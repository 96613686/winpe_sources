# mmioOpenA

- ea: `0x180011f20`
- end: `0x18001216b`
- name: `mmioOpenA`
- size: `587`
- prototype: `HMMIO __stdcall(LPSTR pszFileName, LPMMIOINFO pmmioinfo, DWORD fdwOpen)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18000aef0`
- `0x18000e0d0`
- `0x1800106c0`
- `0x18001102a`
- `0x180011a18`
- `0x180011b64`
- `0x180011f20`
- `0x180012690`
- `0x180012c34`
- `0x180012ca0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ff1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ff1`

## pseudocode

```c
HMMIO __stdcall mmioOpenA(LPSTR pszFileName, LPMMIOINFO pmmioinfo, DWORD fdwOpen)
{
  UINT *p_wErrorRet; // rsi
  WCHAR *v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  CHAR *SpinCount; // rdx
  LONG LockSemaphore_high; // r8d
  MMRESULT v12; // eax
  __int64 (__fastcall *v13)(char *, int, void *, const WCHAR *); // rax
  UINT v14; // eax
  __int64 v15; // rdi
  CHAR MbString[260]; // [rsp+30h] [rbp-358h] BYREF
  WCHAR UnicodeString[260]; // [rsp+140h] [rbp-248h] BYREF

  if ( (fdwOpen & 0xFFFC0000) != 0 )
    return 0;
  p_wErrorRet = &pmmioinfo->wErrorRet;
  if ( pmmioinfo )
    *p_wErrorRet = 0;
  if ( pszFileName )
  {
    AsciiStrToUnicodeStr(UnicodeString);
    v7 = UnicodeString;
  }
  else
  {
    v7 = 0;
  }
  v8 = NewHandle(5, 0, 0x64u);
  if ( !v8 )
  {
    if ( pmmioinfo )
      *p_wErrorRet = 258;
    return 0;
  }
  LeaveCriticalSection(&HandleListCritSec);
  memset_0(v8, 0, 0x64u);
  if ( pmmioinfo )
  {
    *(_OWORD *)&v8->DebugInfo = *(_OWORD *)&pmmioinfo->dwFlags;
    *(_OWORD *)&v8->OwningThread = *(_OWORD *)&pmmioinfo->wErrorRet;
    *(_OWORD *)&v8->SpinCount = *(_OWORD *)&pmmioinfo->pchBuffer;
    *(_OWORD *)&v8[1].LockCount = *(_OWORD *)&pmmioinfo->pchEndRead;
    *(_OWORD *)&v8[1].LockSemaphore = *(_OWORD *)&pmmioinfo->lBufOffset;
    *(_OWORD *)&v8[2].DebugInfo = *(_OWORD *)&pmmioinfo->adwInfo[2];
    LODWORD(v8[2].OwningThread) = HIDWORD(pmmioinfo->hmmio);
  }
  LODWORD(v8->DebugInfo) = fdwOpen;
  *(_QWORD *)&v8[2].RecursionCount = v8;
  if ( (fdwOpen & 0x10000) != 0 )
  {
    if ( !HIDWORD(v8->LockSemaphore) )
      HIDWORD(v8->LockSemaphore) = 0x2000;
    LODWORD(v8->DebugInfo) = fdwOpen & 0xFFFEFFFF;
  }
  SetIOProc(v7, (__int64)v8);
  SpinCount = (CHAR *)v8->SpinCount;
  LockSemaphore_high = HIDWORD(v8->LockSemaphore);
  v8->SpinCount = 0;
  v12 = mmioSetBuffer((HMMIO)v8, SpinCount, LockSemaphore_high, 0);
  if ( v12 )
  {
    if ( pmmioinfo )
      *p_wErrorRet = v12;
    FreeHandle((__int64)v8);
    return 0;
  }
  if ( ((__int64)v8->DebugInfo & 0x1000000) != 0
    || (v13 = *(__int64 (__fastcall **)(char *, int, void *, const WCHAR *))&v8->LockCount, v13 == mmioDOSIOProc)
    || (char *)v13 == (char *)mmioMEMIOProc )
  {
    v14 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, __int64, WCHAR *))&v8->LockCount)(v8, 3, v7);
    if ( v14 )
      goto LABEL_25;
    if ( *(__int64 (__fastcall **)(char *, int, void *, const WCHAR *))&v8->LockCount == mmioDOSIOProc
      && (fdwOpen & 0x20100) != 0 )
    {
      UnicodeStrToAsciiStr(MbString);
      StringCchCopyA(pszFileName, 0x80u, MbString);
    }
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, LPSTR))v13)(v8, 3, pszFileName);
    if ( v14 )
    {
LABEL_25:
      if ( pmmioinfo )
        *p_wErrorRet = v14;
      v15 = 0;
      goto LABEL_28;
    }
  }
  if ( ((__int64)v8->DebugInfo & 0x24300) != 0 )
  {
    v15 = 1;
LABEL_28:
    mmioSetBuffer((HMMIO)v8, 0, 0, 0);
    FreeHandle((__int64)v8);
    return (HMMIO)v15;
  }
  LODWORD(v8[1].LockSemaphore) = HIDWORD(v8[1].LockSemaphore);
  return (HMMIO)v8;
}

```

## disassembly

```asm
0x180011f20  mov     [rsp+arg_10], rbx
0x180011f25  mov     [rsp+arg_18], rbp
0x180011f2a  push    rsi
0x180011f2b  push    rdi
0x180011f2c  push    r13
0x180011f2e  push    r14
0x180011f30  push    r15
0x180011f32  sub     rsp, 360h
0x180011f39  mov     rax, cs:__security_cookie
0x180011f40  xor     rax, rsp
0x180011f43  mov     [rsp+388h+var_38], rax
0x180011f4b  mov     ebp, r8d
0x180011f4e  mov     rdi, rdx
0x180011f51  mov     r14, rcx
0x180011f54  test    r8d, 0FFFC0000h
0x180011f5b  jnz     short loc_180011FBC
0x180011f5d  lea     rsi, [rdx+10h]
0x180011f61  test    rdx, rdx
0x180011f64  jz      short loc_180011F6C
0x180011f66  mov     dword ptr [rsi], 0
0x180011f6c  test    r14, r14
0x180011f6f  jz      short loc_180011F93
0x180011f71  mov     r8, r14
0x180011f74  lea     rdx, [rsp+388h+var_40]
0x180011f7c  lea     rcx, [rsp+388h+UnicodeString]; UnicodeString
0x180011f84  call    AsciiStrToUnicodeStr
0x180011f89  lea     r15, [rsp+388h+UnicodeString]
0x180011f91  jmp     short loc_180011F96
0x180011f93  xor     r15d, r15d
0x180011f96  xor     edx, edx
0x180011f98  mov     r13d, 64h ; 'd'
0x180011f9e  mov     r8d, r13d
0x180011fa1  lea     ecx, [rdx+5]
0x180011fa4  call    NewHandle
0x180011fa9  mov     rbx, rax
0x180011fac  test    rax, rax
0x180011faf  jnz     short loc_180011FEA
0x180011fb1  test    rdi, rdi
0x180011fb4  jz      short loc_180011FBC
0x180011fb6  mov     dword ptr [rsi], 102h
0x180011fbc  xor     eax, eax
0x180011fbe  mov     rcx, [rsp+388h+var_38]
0x180011fc6  xor     rcx, rsp; StackCookie
0x180011fc9  call    __security_check_cookie
0x180011fce  lea     r11, [rsp+388h+var_28]
0x180011fd6  mov     rbx, [r11+40h]
0x180011fda  mov     rbp, [r11+48h]
0x180011fde  mov     rsp, r11
0x180011fe1  pop     r15
0x180011fe3  pop     r14
0x180011fe5  pop     r13
0x180011fe7  pop     rdi
0x180011fe8  pop     rsi
0x180011fe9  retn
0x180011fea  lea     rcx, HandleListCritSec; lpCriticalSection
0x180011ff1  call    cs:__imp_LeaveCriticalSection
0x180011ff7  mov     r8, r13; Size
0x180011ffa  xor     edx, edx; Val
0x180011ffc  mov     rcx, rbx; void *
0x180011fff  call    memset_0
0x180012004  test    rdi, rdi
0x180012007  jz      short loc_18001203D
0x180012009  movups  xmm0, xmmword ptr [rdi]
0x18001200c  movups  xmmword ptr [rbx], xmm0
0x18001200f  movups  xmm1, xmmword ptr [rdi+10h]
0x180012013  movups  xmmword ptr [rbx+10h], xmm1
0x180012017  movups  xmm0, xmmword ptr [rdi+20h]
0x18001201b  movups  xmmword ptr [rbx+20h], xmm0
0x18001201f  movups  xmm1, xmmword ptr [rdi+30h]
0x180012023  movups  xmmword ptr [rbx+30h], xmm1
0x180012027  movups  xmm0, xmmword ptr [rdi+40h]
0x18001202b  movups  xmmword ptr [rbx+40h], xmm0
0x18001202f  movups  xmm1, xmmword ptr [rdi+50h]
0x180012033  movups  xmmword ptr [rbx+50h], xmm1
0x180012037  mov     eax, [rdi+60h]
0x18001203a  mov     [rbx+60h], eax
0x18001203d  mov     [rbx], ebp
0x18001203f  mov     [rbx+5Ch], rbx
0x180012043  bt      ebp, 10h
0x180012047  jnb     short loc_18001205E
0x180012049  cmp     dword ptr [rbx+1Ch], 0
0x18001204d  jnz     short loc_180012056
0x18001204f  mov     dword ptr [rbx+1Ch], 2000h
0x180012056  mov     eax, ebp
0x180012058  btr     eax, 10h
0x18001205c  mov     [rbx], eax
0x18001205e  mov     rdx, rbx
0x180012061  mov     rcx, r15
0x180012064  call    SetIOProc
0x180012069  mov     rdx, [rbx+20h]; pchBuffer
0x18001206d  xor     r9d, r9d; fuBuffer
0x180012070  mov     r8d, [rbx+1Ch]; cchBuffer
0x180012074  mov     rcx, rbx; hmmio
0x180012077  mov     qword ptr [rbx+20h], 0
0x18001207f  call    mmioSetBuffer
0x180012084  test    eax, eax
0x180012086  jz      short loc_18001209C
0x180012088  test    rdi, rdi
0x18001208b  jz      short loc_18001208F
0x18001208d  mov     [rsi], eax
0x18001208f  mov     rcx, rbx
0x180012092  call    FreeHandle
0x180012097  jmp     loc_180011FBC
0x18001209c  test    dword ptr [rbx], 1000000h
0x1800120a2  lea     r13, ?mmioDOSIOProc@@YA_JPEADI_J1@Z; mmioDOSIOProc(char *,uint,__int64,__int64)
0x1800120a9  jnz     short loc_1800120FF
0x1800120ab  mov     rax, [rbx+8]
0x1800120af  cmp     rax, r13
0x1800120b2  jz      short loc_1800120FF
0x1800120b4  lea     rcx, ?mmioMEMIOProc@@YA_JPEADI_J1@Z; mmioMEMIOProc(char *,uint,__int64,__int64)
0x1800120bb  cmp     rax, rcx
0x1800120be  jz      short loc_1800120FF
0x1800120c0  xor     r9d, r9d
0x1800120c3  mov     r8, r14
0x1800120c6  mov     rcx, rbx
0x1800120c9  lea     edx, [r9+3]
0x1800120cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d2  test    eax, eax
0x1800120d4  jz      short loc_18001214E
0x1800120d6  test    rdi, rdi
0x1800120d9  jz      short loc_1800120DD
0x1800120db  mov     [rsi], eax
0x1800120dd  xor     edi, edi
0x1800120df  xor     r9d, r9d; fuBuffer
0x1800120e2  xor     r8d, r8d; cchBuffer
0x1800120e5  xor     edx, edx; pchBuffer
0x1800120e7  mov     rcx, rbx; hmmio
0x1800120ea  call    mmioSetBuffer
0x1800120ef  mov     rcx, rbx
0x1800120f2  call    FreeHandle
0x1800120f7  mov     rax, rdi
0x1800120fa  jmp     loc_180011FBE
0x1800120ff  mov     rax, [rbx+8]
0x180012103  xor     r9d, r9d
0x180012106  mov     r8, r15
0x180012109  mov     rcx, rbx
0x18001210c  lea     edx, [r9+3]
0x180012110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012115  test    eax, eax
0x180012117  jnz     short loc_1800120D6
0x180012119  cmp     [rbx+8], r13
0x18001211d  jnz     short loc_18001214E
0x18001211f  test    ebp, 20100h
0x180012125  jz      short loc_18001214E
0x180012127  mov     r8, r15
0x18001212a  lea     rdx, [rsp+388h+var_254]
0x180012132  lea     rcx, [rsp+388h+MbString]; MbString
0x180012137  call    UnicodeStrToAsciiStr
0x18001213c  lea     r8, [rsp+388h+MbString]; char *
0x180012141  mov     edx, 80h; unsigned __int64
0x180012146  mov     rcx, r14; char *
0x180012149  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001214e  test    dword ptr [rbx], 24300h
0x180012154  jz      short loc_18001215D
0x180012156  mov     edi, 1
0x18001215b  jmp     short loc_1800120DF
0x18001215d  mov     eax, [rbx+44h]
0x180012160  mov     [rbx+40h], eax
0x180012163  mov     rax, rbx
0x180012166  jmp     loc_180011FBE
```
