# CManagedAppProcessor::WriteRsopLogs(void)

- ea: `0x180011fc0`
- end: `0x1800121f9`
- name: `?WriteRsopLogs@CManagedAppProcessor@@QEAAXXZ`
- size: `569`
- prototype: `void __fastcall(CManagedAppProcessor *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b7e8`
- `0x18001069c`

## callees

- `0x18000b648`
- `0x18000c0b0`
- `0x18000c3bc`
- `0x180011f28`
- `0x180011fc0`
- `0x1800295b4`
- `0x18002962c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012198`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012198`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012017`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012017`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800121a1`
- `USERENV!LeaveCriticalPolicySection` at `0x1800121d4`
- `USERENV!LeaveCriticalPolicySection` at `0x1800121d4`

## pseudocode

```c
void __fastcall CManagedAppProcessor::WriteRsopLogs(CManagedAppProcessor *this)
{
  int v2; // edi
  HKEY *v3; // rsi
  int v4; // eax
  int *v5; // rcx
  _DWORD *v6; // rax
  int v7; // eax
  int *v8; // rcx
  int NameSpace; // eax
  HLOCAL v10; // rdi
  __int64 v11; // rax
  void *v12; // rcx
  _QWORD v13[2]; // [rsp+30h] [rbp-19h] BYREF
  __int128 v14; // [rsp+40h] [rbp-9h]
  __int128 v15; // [rsp+50h] [rbp+7h]
  __int128 v16; // [rsp+60h] [rbp+17h] BYREF
  int v17; // [rsp+70h] [rbp+27h]
  HKEY *v18; // [rsp+78h] [rbp+2Fh]
  __int128 *v19; // [rsp+80h] [rbp+37h]
  HLOCAL hMem; // [rsp+B0h] [rbp+67h] BYREF

  v2 = *((_DWORD *)this + 75);
  v3 = (HKEY *)((char *)this + 360);
  if ( *((_DWORD *)this + 99) == 2 && !v2 && *((_DWORD *)this + 110) == 1 && !*((_DWORD *)this + 117) )
    RegDeleteValueW(*((HKEY *)this + 54), L"DiagnosticNamespace");
  if ( !*((_DWORD *)this + 77)
    || (int)CRsopContext::GetExclusiveLoggingAccess((CRsopContext *)v3, *((_QWORD *)this + 33) == 0) >= 0 )
  {
    if ( !*((_DWORD *)this + 98) )
      goto LABEL_38;
    if ( v2 )
    {
      v6 = (_DWORD *)*((_QWORD *)this + 50);
      if ( v6 )
        *v6 = 0;
      goto LABEL_16;
    }
    v4 = CAppList::WriteLog((struct CAppInfo **)this + 4, 0);
    if ( v4 < 0 )
    {
      if ( *((_DWORD *)this + 98) )
      {
        v5 = (int *)*((_QWORD *)this + 50);
        if ( v5 )
          *v5 = v4;
      }
LABEL_16:
      *((_DWORD *)this + 98) = 0;
    }
  }
  if ( !*((_DWORD *)this + 98) )
    goto LABEL_38;
  if ( *((_DWORD *)this + 99) == 1 && *((_DWORD *)this + 77) )
  {
    v13[1] = 0;
    v14 = 0;
    v15 = 0;
    v13[0] = &CCategoryInfoLog::`vftable';
    v17 = 0;
    v18 = v3;
    v19 = &v16;
    v16 = 0;
    v7 = CCategoryInfoLog::WriteLog((CCategoryInfoLog *)v13);
    if ( v7 < 0 )
    {
      if ( *((_DWORD *)this + 98) )
      {
        v8 = (int *)*((_QWORD *)this + 50);
        if ( v8 )
          *v8 = v7;
      }
      *((_DWORD *)this + 98) = 0;
    }
    CCategoryInfoLog::~CCategoryInfoLog((CCategoryInfoLog *)v13);
  }
  if ( !*((_DWORD *)this + 98) || *((_DWORD *)this + 117) )
  {
LABEL_38:
    if ( !*((_DWORD *)this + 77) )
      return;
    goto LABEL_39;
  }
  if ( !*((_DWORD *)this + 77) )
  {
    if ( *((_DWORD *)this + 99) != 1 )
    {
      hMem = 0;
      NameSpace = CRsopContext::GetNameSpace((CRsopContext *)v3, (unsigned __int16 **)&hMem);
      v10 = hMem;
      if ( NameSpace >= 0 )
      {
        if ( hMem )
        {
          v11 = -1;
          do
            ++v11;
          while ( *((_WORD *)hMem + v11) );
        }
        else
        {
          LODWORD(v11) = 0;
        }
        RegSetValueExW(v3[9], L"DiagnosticNamespace", 0, 1u, (const BYTE *)hMem, 2 * v11 + 2);
      }
      LocalFree(v10);
      if ( *((_DWORD *)this + 74) )
        CRsopAppContext::WriteCurrentRsopVersion((CRsopAppContext *)v3, *((HKEY *)this + 36));
    }
    goto LABEL_38;
  }
LABEL_39:
  v12 = (void *)*((_QWORD *)this + 53);
  if ( v12 )
  {
    LeaveCriticalPolicySection(v12);
    *((_QWORD *)this + 53) = 0;
  }
}

```

## disassembly

```asm
0x180011fc0  mov     [rsp-8+arg_8], rbx
0x180011fc5  mov     [rsp-8+arg_10], rsi
0x180011fca  push    rbp
0x180011fcb  push    rdi
0x180011fcc  push    r14
0x180011fce  lea     rbp, [rsp-47h]
0x180011fd3  sub     rsp, 90h
0x180011fda  mov     rbx, rcx
0x180011fdd  mov     edi, [rcx+12Ch]
0x180011fe3  lea     rsi, [rcx+168h]
0x180011fea  xor     r14d, r14d
0x180011fed  cmp     dword ptr [rsi+24h], 2
0x180011ff1  jnz     short loc_18001201D
0x180011ff3  test    edi, edi
0x180011ff5  jnz     short loc_18001201D
0x180011ff7  cmp     dword ptr [rcx+1B8h], 1
0x180011ffe  jnz     short loc_18001201D
0x180012000  cmp     [rcx+1D4h], r14d
0x180012007  jnz     short loc_18001201D
0x180012009  lea     rdx, aDiagnosticname; "DiagnosticNamespace"
0x180012010  mov     rcx, [rcx+1B0h]; hKey
0x180012017  call    cs:__imp_RegDeleteValueW
0x18001201d  cmp     [rbx+134h], r14d
0x180012024  jz      short loc_18001203F
0x180012026  mov     edx, r14d
0x180012029  cmp     [rbx+108h], r14
0x180012030  setz    dl; int
0x180012033  mov     rcx, rsi; this
0x180012036  call    ?GetExclusiveLoggingAccess@CRsopContext@@QEAAJH@Z; CRsopContext::GetExclusiveLoggingAccess(int)
0x18001203b  test    eax, eax
0x18001203d  js      short loc_18001208E
0x18001203f  cmp     [rbx+188h], r14d
0x180012046  jz      loc_1800121BF
0x18001204c  test    edi, edi
0x18001204e  jnz     short loc_180012078
0x180012050  lea     rcx, [rbx+20h]; this
0x180012054  xor     edx, edx; unsigned int
0x180012056  call    ?WriteLog@CAppList@@QEAAJK@Z; CAppList::WriteLog(ulong)
0x18001205b  test    eax, eax
0x18001205d  jns     short loc_18001208E
0x18001205f  cmp     [rbx+188h], r14d
0x180012066  jz      short loc_180012087
0x180012068  mov     rcx, [rbx+190h]
0x18001206f  test    rcx, rcx
0x180012072  jz      short loc_180012087
0x180012074  mov     [rcx], eax
0x180012076  jmp     short loc_180012087
0x180012078  mov     rax, [rbx+190h]
0x18001207f  test    rax, rax
0x180012082  jz      short loc_180012087
0x180012084  mov     [rax], r14d
0x180012087  mov     [rbx+188h], r14d
0x18001208e  cmp     [rbx+188h], r14d
0x180012095  jz      loc_1800121BF
0x18001209b  cmp     dword ptr [rbx+18Ch], 1
0x1800120a2  jnz     short loc_180012114
0x1800120a4  cmp     [rbx+134h], r14d
0x1800120ab  jz      short loc_180012114
0x1800120ad  mov     [rbp+57h+var_68], r14
0x1800120b1  xorps   xmm0, xmm0
0x1800120b4  movdqa  [rbp+57h+var_60], xmm0
0x1800120b9  xorps   xmm1, xmm1
0x1800120bc  movdqa  [rbp+57h+var_50], xmm1
0x1800120c1  lea     rax, ??_7CCategoryInfoLog@@6B@; const CCategoryInfoLog::`vftable'
0x1800120c8  mov     [rbp+57h+var_70], rax
0x1800120cc  mov     [rbp+57h+var_30], r14d
0x1800120d0  mov     [rbp+57h+var_28], rsi
0x1800120d4  lea     rax, [rbp+57h+var_40]
0x1800120d8  mov     [rbp+57h+var_20], rax
0x1800120dc  movups  [rbp+57h+var_40], xmm0
0x1800120e0  lea     rcx, [rbp+57h+var_70]; this
0x1800120e4  call    ?WriteLog@CCategoryInfoLog@@QEAAJXZ; CCategoryInfoLog::WriteLog(void)
0x1800120e9  test    eax, eax
0x1800120eb  jns     short loc_18001210B
0x1800120ed  cmp     [rbx+188h], r14d
0x1800120f4  jz      short loc_180012104
0x1800120f6  mov     rcx, [rbx+190h]
0x1800120fd  test    rcx, rcx
0x180012100  jz      short loc_180012104
0x180012102  mov     [rcx], eax
0x180012104  mov     [rbx+188h], r14d
0x18001210b  lea     rcx, [rbp+57h+var_70]; this
0x18001210f  call    ??1CCategoryInfoLog@@UEAA@XZ; CCategoryInfoLog::~CCategoryInfoLog(void)
0x180012114  cmp     [rbx+188h], r14d
0x18001211b  jz      loc_1800121BF
0x180012121  cmp     [rbx+1D4h], r14d
0x180012128  jnz     loc_1800121BF
0x18001212e  cmp     [rbx+134h], r14d
0x180012135  jnz     loc_1800121C8
0x18001213b  cmp     dword ptr [rbx+18Ch], 1
0x180012142  jz      short loc_1800121BF
0x180012144  mov     [rbp+57h+hMem], r14
0x180012148  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x18001214c  mov     rcx, rsi; this
0x18001214f  call    ?GetNameSpace@CRsopContext@@QEAAJPEAPEAG@Z; CRsopContext::GetNameSpace(ushort * *)
0x180012154  mov     rdi, [rbp+57h+hMem]
0x180012158  test    eax, eax
0x18001215a  js      short loc_18001219E
0x18001215c  test    rdi, rdi
0x18001215f  jnz     short loc_180012166
0x180012161  mov     rax, r14
0x180012164  jmp     short loc_180012174
0x180012166  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001216a  inc     rax
0x18001216d  cmp     [rdi+rax*2], r14w
0x180012172  jnz     short loc_18001216A
0x180012174  lea     eax, ds:2[rax*2]
0x18001217b  mov     [rsp+0A0h+cbData], eax; cbData
0x18001217f  mov     [rsp+0A0h+lpData], rdi; lpData
0x180012184  mov     r9d, 1; dwType
0x18001218a  xor     r8d, r8d; Reserved
0x18001218d  lea     rdx, aDiagnosticname; "DiagnosticNamespace"
0x180012194  mov     rcx, [rsi+48h]; hKey
0x180012198  call    cs:__imp_RegSetValueExW
0x18001219e  mov     rcx, rdi; hMem
0x1800121a1  call    cs:__imp_LocalFree
0x1800121a7  cmp     [rbx+128h], r14d
0x1800121ae  jz      short loc_1800121BF
0x1800121b0  mov     rdx, [rbx+120h]; HKEY
0x1800121b7  mov     rcx, rsi; this
0x1800121ba  call    ?WriteCurrentRsopVersion@CRsopAppContext@@QEAAKPEAUHKEY__@@@Z; CRsopAppContext::WriteCurrentRsopVersion(HKEY__ *)
0x1800121bf  cmp     [rbx+134h], r14d
0x1800121c6  jz      short loc_1800121E1
0x1800121c8  mov     rcx, [rbx+1A8h]; hSection
0x1800121cf  test    rcx, rcx
0x1800121d2  jz      short loc_1800121E1
0x1800121d4  call    cs:__imp_LeaveCriticalPolicySection
0x1800121da  mov     [rbx+1A8h], r14
0x1800121e1  lea     r11, [rsp+0A0h+var_10]
0x1800121e9  mov     rbx, [r11+28h]
0x1800121ed  mov     rsi, [r11+30h]
0x1800121f1  mov     rsp, r11
0x1800121f4  pop     r14
0x1800121f6  pop     rdi
0x1800121f7  pop     rbp
0x1800121f8  retn
```
