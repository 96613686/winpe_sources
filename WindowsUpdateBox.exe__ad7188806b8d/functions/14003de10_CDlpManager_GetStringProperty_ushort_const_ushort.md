# CDlpManager::GetStringProperty(ushort const *,ushort * *)

- ea: `0x14003de10`
- end: `0x14003e08a`
- name: `?GetStringProperty@CDlpManager@@UEAAJPEBGPEAPEAG@Z`
- size: `634`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x14003de10`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14003dfce`
- `KERNEL32!LeaveCriticalSection` at `0x14003dfce`
- `KERNEL32!EnterCriticalSection` at `0x14003de47`
- `KERNEL32!EnterCriticalSection` at `0x14003de47`
- `KERNEL32!CompareStringW` at `0x14003df84`
- `KERNEL32!CompareStringW` at `0x14003df84`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e024`
- `OLEAUT32!__imp_SysAllocString` at `0x14003e024`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dfb6`
- `OLEAUT32!__imp_SysFreeString` at `0x14003dfb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::GetStringProperty(CDlpManager *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r13
  unsigned int v7; // edi
  __int64 v8; // rax
  unsigned int v9; // esi
  int v10; // eax
  unsigned int v11; // r14d
  int v12; // ebp
  __int64 v13; // rax
  const WCHAR *v14; // rax
  __int64 v16; // rax
  const OLECHAR *v17; // rcx
  unsigned __int16 *v18; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-68h]
  __int64 cchCount2; // [rsp+28h] [rbp-60h]

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  v7 = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = -2147024809;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
        goto LABEL_20;
      v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v9 = 0;
      if ( !v8 )
        goto LABEL_7;
      LODWORD(cchCount2) = -2147024809;
      LODWORD(lpString2) = 1357;
      goto LABEL_5;
    }
    v11 = *((_DWORD *)this + 135);
    v12 = 0;
    if ( !v11 )
    {
LABEL_19:
      v7 = -2147023728;
      goto LABEL_20;
    }
    while ( 1 )
    {
      v13 = *((_QWORD *)this + 68);
      if ( !v13 )
        v13 = 0;
      v14 = *(const WCHAR **)(v13 + 8LL * v12);
      if ( !v14 )
        v14 = 0;
      if ( CompareStringW(0x409u, 1u, a2, -1, v14, -1) == 2 )
        break;
      if ( ++v12 >= v11 )
        goto LABEL_19;
    }
    v16 = *((_QWORD *)this + 70);
    if ( !v16 )
      v16 = 0;
    v17 = *(const OLECHAR **)(v16 + 8LL * v12);
    if ( !v17 )
      v17 = 0;
    v18 = SysAllocString(v17);
    if ( v18 )
    {
      *a3 = v18;
      goto LABEL_20;
    }
    v7 = -2147024882;
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
    {
      v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v9 = 0;
      if ( v8 )
      {
        LODWORD(cchCount2) = -2147024882;
        LODWORD(lpString2) = 1368;
LABEL_5:
        v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v8,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpManager::GetStringProperty",
                lpString2,
                cchCount2,
                -2);
        v9 = v10;
        if ( v10 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
      }
LABEL_7:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
    }
  }
  else
  {
    v7 = -2147024809;
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
    {
      v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v9 = 0;
      if ( v8 )
      {
        LODWORD(cchCount2) = -2147024809;
        LODWORD(lpString2) = 1356;
        goto LABEL_5;
      }
      goto LABEL_7;
    }
  }
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  LeaveCriticalSection(v6);
  return v7;
}

```

## disassembly

```asm
0x14003de10  mov     rax, rsp
0x14003de13  push    rdi
0x14003de14  push    r12
0x14003de16  push    r13
0x14003de18  push    r14
0x14003de1a  push    r15
0x14003de1c  sub     rsp, 60h
0x14003de20  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x14003de28  mov     [rax+10h], rbx
0x14003de2c  mov     [rax+18h], rbp
0x14003de30  mov     [rax+20h], rsi
0x14003de34  mov     r15, r8
0x14003de37  mov     r12, rdx
0x14003de3a  mov     rsi, rcx
0x14003de3d  lea     r13, [rcx+1D8h]
0x14003de44  mov     rcx, r13; lpCriticalSection
0x14003de47  call    cs:__imp_EnterCriticalSection
0x14003de4e  nop     dword ptr [rax+rax+00h]
0x14003de53  mov     [rsp+88h+var_40], 1
0x14003de5b  xor     r14d, r14d
0x14003de5e  mov     ebx, r14d
0x14003de61  mov     edi, r14d
0x14003de64  test    r12, r12
0x14003de67  jnz     short loc_14003DEE3
0x14003de69  mov     ebp, 80070057h
0x14003de6e  mov     edi, ebp
0x14003de70  mov     rax, [rsi+48h]
0x14003de74  lea     rcx, [rsi+48h]
0x14003de78  mov     rax, [rax+10h]
0x14003de7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003de81  test    rax, rax
0x14003de84  jz      loc_14003DFA7
0x14003de8a  mov     rax, [rsi+48h]
0x14003de8e  lea     rcx, [rsi+48h]
0x14003de92  mov     rax, [rax+10h]
0x14003de96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003de9b  mov     esi, r14d
0x14003de9e  test    rax, rax
0x14003dea1  jz      short loc_14003DED7
0x14003dea3  mov     dword ptr [rsp+88h+cchCount2], ebp
0x14003dea7  mov     dword ptr [rsp+88h+lpString2], 54Ch
0x14003deaf  lea     r9, aCdlpmanagerGet_8; "CDlpManager::GetStringProperty"
0x14003deb6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14003debd  mov     edx, 4
0x14003dec2  mov     rcx, rax
0x14003dec5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003deca  test    eax, eax
0x14003decc  mov     esi, eax
0x14003dece  jns     short loc_14003DED7
0x14003ded0  mov     ecx, eax
0x14003ded2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14003ded7  mov     ecx, esi
0x14003ded9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003dede  jmp     loc_14003DFA7
0x14003dee3  test    r15, r15
0x14003dee6  jnz     short loc_14003DF33
0x14003dee8  mov     ebp, 80070057h
0x14003deed  mov     edi, ebp
0x14003deef  mov     rax, [rsi+48h]
0x14003def3  lea     rcx, [rsi+48h]
0x14003def7  mov     rax, [rax+10h]
0x14003defb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003df00  test    rax, rax
0x14003df03  jz      loc_14003DFA7
0x14003df09  mov     rax, [rsi+48h]
0x14003df0d  lea     rcx, [rsi+48h]
0x14003df11  mov     rax, [rax+10h]
0x14003df15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003df1a  mov     esi, r14d
0x14003df1d  test    rax, rax
0x14003df20  jz      short loc_14003DED7
0x14003df22  mov     dword ptr [rsp+88h+cchCount2], ebp
0x14003df26  mov     dword ptr [rsp+88h+lpString2], 54Dh
0x14003df2e  jmp     loc_14003DEAF
0x14003df33  mov     r14d, [rsi+21Ch]
0x14003df3a  xor     edx, edx
0x14003df3c  mov     ebp, edx
0x14003df3e  test    r14d, r14d
0x14003df41  jz      short loc_14003DF9F
0x14003df43  mov     rax, [rsi+220h]
0x14003df4a  test    rax, rax
0x14003df4d  cmovz   rax, rdx
0x14003df51  movsxd  rcx, ebp
0x14003df54  mov     [rsp+88h+arg_0], rcx
0x14003df5c  mov     rax, [rax+rcx*8]
0x14003df60  test    rax, rax
0x14003df63  cmovz   rax, rdx
0x14003df67  mov     dword ptr [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x14003df6f  mov     [rsp+88h+lpString2], rax; lpString2
0x14003df74  or      r9d, 0FFFFFFFFh; cchCount1
0x14003df78  mov     r8, r12; lpString1
0x14003df7b  lea     edx, [r9+2]; dwCmpFlags
0x14003df7f  mov     ecx, 409h; Locale
0x14003df84  call    cs:__imp_CompareStringW
0x14003df8b  nop     dword ptr [rax+rax+00h]
0x14003df90  cmp     eax, 2
0x14003df93  jz      short loc_14003E000
0x14003df95  inc     ebp
0x14003df97  cmp     ebp, r14d
0x14003df9a  mov     rdx, rbx
0x14003df9d  jb      short loc_14003DF43
0x14003df9f  mov     edi, 80070490h
0x14003dfa4  xor     r14d, r14d
0x14003dfa7  mov     ecx, edi
0x14003dfa9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003dfae  test    rbx, rbx
0x14003dfb1  jz      short loc_14003DFC3
0x14003dfb3  mov     rcx, rbx; bstrString
0x14003dfb6  call    cs:__imp_SysFreeString
0x14003dfbd  nop     dword ptr [rax+rax+00h]
0x14003dfc2  nop
0x14003dfc3  mov     edx, [rsp+88h+var_40]
0x14003dfc7  test    edx, edx
0x14003dfc9  jz      short loc_14003DFDF
0x14003dfcb  mov     rcx, r13; lpCriticalSection
0x14003dfce  call    cs:__imp_LeaveCriticalSection
0x14003dfd5  nop     dword ptr [rax+rax+00h]
0x14003dfda  mov     [rsp+88h+var_40], r14d
0x14003dfdf  mov     eax, edi
0x14003dfe1  lea     r11, [rsp+88h+var_28]
0x14003dfe6  mov     rbx, [r11+38h]
0x14003dfea  mov     rbp, [r11+40h]
0x14003dfee  mov     rsi, [r11+48h]
0x14003dff2  mov     rsp, r11
0x14003dff5  pop     r15
0x14003dff7  pop     r14
0x14003dff9  pop     r13
0x14003dffb  pop     r12
0x14003dffd  pop     rdi
0x14003dffe  retn
0x14003e000  mov     rax, [rsi+230h]
0x14003e007  xor     r14d, r14d
0x14003e00a  test    rax, rax
0x14003e00d  cmovz   rax, r14
0x14003e011  mov     rcx, [rsp+88h+arg_0]
0x14003e019  mov     rcx, [rax+rcx*8]
0x14003e01d  test    rcx, rcx
0x14003e020  cmovz   rcx, r14; psz
0x14003e024  call    cs:__imp_SysAllocString
0x14003e02b  nop     dword ptr [rax+rax+00h]
0x14003e030  test    rax, rax
0x14003e033  jnz     short loc_14003E082
0x14003e035  mov     edi, 8007000Eh
0x14003e03a  mov     rax, [rsi+48h]
0x14003e03e  lea     rcx, [rsi+48h]
0x14003e042  mov     rax, [rax+10h]
0x14003e046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e04b  test    rax, rax
0x14003e04e  jz      loc_14003DFA7
0x14003e054  mov     rax, [rsi+48h]
0x14003e058  lea     rcx, [rsi+48h]
0x14003e05c  mov     rax, [rax+10h]
0x14003e060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e065  mov     esi, r14d
0x14003e068  test    rax, rax
0x14003e06b  jz      loc_14003DED7
0x14003e071  mov     dword ptr [rsp+88h+cchCount2], edi
0x14003e075  mov     dword ptr [rsp+88h+lpString2], 558h
0x14003e07d  jmp     loc_14003DEAF
0x14003e082  mov     [r15], rax
0x14003e085  jmp     loc_14003DFA7
```
