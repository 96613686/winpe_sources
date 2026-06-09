# CDlpTask::GetFileByName(ushort const *,IDlpFile * *)

- ea: `0x14003b9a0`
- end: `0x14003bd59`
- name: `?GetFileByName@CDlpTask@@UEAAJPEBGPEAPEAVIDlpFile@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, PCNZWCH lpString1, struct IDlpFile **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002db30`
- `0x140034ab4`
- `0x14003b9a0`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14003bca0`
- `KERNEL32!LeaveCriticalSection` at `0x14003bca0`
- `KERNEL32!EnterCriticalSection` at `0x14003b9d7`
- `KERNEL32!EnterCriticalSection` at `0x14003b9d7`
- `KERNEL32!CompareStringW` at `0x14003bc44`
- `KERNEL32!CompareStringW` at `0x14003bc44`
- `OLEAUT32!__imp_SysFreeString` at `0x14003bbca`
- `OLEAUT32!__imp_SysFreeString` at `0x14003bc81`
- `OLEAUT32!__imp_SysFreeString` at `0x14003bbca`
- `OLEAUT32!__imp_SysFreeString` at `0x14003bc81`

## string_xrefs

- `0x14003ba51`: `CDlpTask::GetFileByName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::GetFileByName(CDlpTask *this, PCNZWCH lpString1, struct IDlpFile **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  int v7; // ebx
  __int64 v8; // rax
  unsigned int v9; // edi
  int v10; // eax
  unsigned int v11; // r14d
  int v12; // esi
  OLECHAR *v13; // rax
  __int64 v14; // rcx
  __int64 v16; // rcx
  struct IDlpFile *v17; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-68h]
  __int64 cchCount2; // [rsp+28h] [rbp-60h]
  BSTR bstrString; // [rsp+90h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  bstrString = 0;
  if ( !lpString1 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_34;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1854;
    goto LABEL_5;
  }
  if ( !*lpString1 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_34;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1855;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_34;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1856;
    goto LABEL_5;
  }
  v7 = CDlpTask::CheckInitialized(this, 0);
  if ( v7 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_34;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = v7;
    LODWORD(lpString2) = 1860;
LABEL_5:
    v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v8,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::GetFileByName",
            lpString2,
            cchCount2,
            -2);
    v9 = v10;
    if ( v10 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_7;
  }
  v11 = *((_DWORD *)this + 91);
  v12 = 0;
  if ( !v11 )
  {
LABEL_33:
    v7 = -2147023728;
    goto LABEL_34;
  }
  v13 = bstrString;
  while ( 1 )
  {
    if ( v13 )
    {
      SysFreeString(v13);
      bstrString = 0;
    }
    v14 = *((_QWORD *)this + 46);
    if ( !v14 )
      v14 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)(v14 + 8LL * v12) + 32LL))(
           *(_QWORD *)(v14 + 8LL * v12),
           &bstrString);
    if ( v7 == -2147023728 )
    {
      v7 = 0;
      goto LABEL_29;
    }
    if ( v7 < 0 )
      break;
LABEL_29:
    v13 = bstrString;
    if ( bstrString )
    {
      if ( CompareStringW(0x409u, 1u, lpString1, -1, bstrString, -1) == 2 )
      {
        _mm_lfence();
        v16 = *((_QWORD *)this + 46);
        if ( !v16 )
          v16 = 0;
        v17 = *(struct IDlpFile **)(v16 + 8LL * v12);
        if ( !v17 )
          v17 = 0;
        *a3 = v17;
        (*(void (__fastcall **)(struct IDlpFile *))(*(_QWORD *)v17 + 8LL))(v17);
        goto LABEL_34;
      }
      v13 = bstrString;
    }
    if ( ++v12 >= v11 )
      goto LABEL_33;
  }
  if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
    goto LABEL_34;
  v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
  v9 = 0;
  if ( v8 )
  {
    LODWORD(cchCount2) = v7;
    LODWORD(lpString2) = 1872;
    goto LABEL_5;
  }
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
LABEL_34:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003b9a0  mov     rax, rsp
0x14003b9a3  push    rdi
0x14003b9a4  push    r12
0x14003b9a6  push    r13
0x14003b9a8  push    r14
0x14003b9aa  push    r15
0x14003b9ac  sub     rsp, 60h
0x14003b9b0  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x14003b9b8  mov     [rax+10h], rbx
0x14003b9bc  mov     [rax+18h], rbp
0x14003b9c0  mov     [rax+20h], rsi
0x14003b9c4  mov     r15, r8
0x14003b9c7  mov     rbp, rdx
0x14003b9ca  mov     rdi, rcx
0x14003b9cd  lea     r12, [rcx+1E8h]
0x14003b9d4  mov     rcx, r12; lpCriticalSection
0x14003b9d7  call    cs:__imp_EnterCriticalSection
0x14003b9de  nop     dword ptr [rax+rax+00h]
0x14003b9e3  mov     [rsp+88h+var_40], 1
0x14003b9eb  xor     r13d, r13d
0x14003b9ee  mov     [rsp+88h+bstrString], r13
0x14003b9f6  test    rbp, rbp
0x14003b9f9  jnz     loc_14003BA85
0x14003b9ff  mov     esi, 80070057h
0x14003ba04  mov     ebx, esi
0x14003ba06  mov     rax, [rdi+0B0h]
0x14003ba0d  lea     rcx, [rdi+0B0h]
0x14003ba14  mov     rax, [rax+10h]
0x14003ba18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ba1d  test    rax, rax
0x14003ba20  jz      loc_14003BC6D
0x14003ba26  mov     rax, [rdi+0B0h]
0x14003ba2d  lea     rcx, [rdi+0B0h]
0x14003ba34  mov     rax, [rax+10h]
0x14003ba38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ba3d  mov     edi, r13d
0x14003ba40  test    rax, rax
0x14003ba43  jz      short loc_14003BA79
0x14003ba45  mov     dword ptr [rsp+88h+cchCount2], esi
0x14003ba49  mov     dword ptr [rsp+88h+lpString2], 73Eh
0x14003ba51  lea     r9, aCdlptaskGetfil_0; "CDlpTask::GetFileByName"
0x14003ba58  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14003ba5f  mov     edx, 4
0x14003ba64  mov     rcx, rax
0x14003ba67  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003ba6c  test    eax, eax
0x14003ba6e  mov     edi, eax
0x14003ba70  jns     short loc_14003BA79
0x14003ba72  mov     ecx, eax
0x14003ba74  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14003ba79  mov     ecx, edi
0x14003ba7b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003ba80  jmp     loc_14003BC6D
0x14003ba85  cmp     [rbp+0], r13w
0x14003ba8a  jnz     short loc_14003BAE3
0x14003ba8c  mov     esi, 80070057h
0x14003ba91  mov     ebx, esi
0x14003ba93  mov     rax, [rdi+0B0h]
0x14003ba9a  lea     rcx, [rdi+0B0h]
0x14003baa1  mov     rax, [rax+10h]
0x14003baa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003baaa  test    rax, rax
0x14003baad  jz      loc_14003BC6D
0x14003bab3  mov     rax, [rdi+0B0h]
0x14003baba  lea     rcx, [rdi+0B0h]
0x14003bac1  mov     rax, [rax+10h]
0x14003bac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003baca  mov     edi, r13d
0x14003bacd  test    rax, rax
0x14003bad0  jz      short loc_14003BA79
0x14003bad2  mov     dword ptr [rsp+88h+cchCount2], esi
0x14003bad6  mov     dword ptr [rsp+88h+lpString2], 73Fh
0x14003bade  jmp     loc_14003BA51
0x14003bae3  test    r15, r15
0x14003bae6  jnz     short loc_14003BB43
0x14003bae8  mov     esi, 80070057h
0x14003baed  mov     ebx, esi
0x14003baef  mov     rax, [rdi+0B0h]
0x14003baf6  lea     rcx, [rdi+0B0h]
0x14003bafd  mov     rax, [rax+10h]
0x14003bb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb06  test    rax, rax
0x14003bb09  jz      loc_14003BC6D
0x14003bb0f  mov     rax, [rdi+0B0h]
0x14003bb16  lea     rcx, [rdi+0B0h]
0x14003bb1d  mov     rax, [rax+10h]
0x14003bb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb26  mov     edi, r13d
0x14003bb29  test    rax, rax
0x14003bb2c  jz      loc_14003BA79
0x14003bb32  mov     dword ptr [rsp+88h+cchCount2], esi
0x14003bb36  mov     dword ptr [rsp+88h+lpString2], 740h
0x14003bb3e  jmp     loc_14003BA51
0x14003bb43  xor     edx, edx; enum WINDLP_STATE *
0x14003bb45  mov     rcx, rdi; this
0x14003bb48  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x14003bb4d  mov     ebx, eax
0x14003bb4f  test    eax, eax
0x14003bb51  jns     short loc_14003BBA7
0x14003bb53  mov     rdx, [rdi+0B0h]
0x14003bb5a  lea     rcx, [rdi+0B0h]
0x14003bb61  mov     rax, [rdx+10h]
0x14003bb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb6a  test    rax, rax
0x14003bb6d  jz      loc_14003BC6D
0x14003bb73  mov     rax, [rdi+0B0h]
0x14003bb7a  lea     rcx, [rdi+0B0h]
0x14003bb81  mov     rax, [rax+10h]
0x14003bb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bb8a  mov     edi, r13d
0x14003bb8d  test    rax, rax
0x14003bb90  jz      loc_14003BA79
0x14003bb96  mov     dword ptr [rsp+88h+cchCount2], ebx
0x14003bb9a  mov     dword ptr [rsp+88h+lpString2], 744h
0x14003bba2  jmp     loc_14003BA51
0x14003bba7  mov     r14d, [rdi+16Ch]
0x14003bbae  mov     esi, r13d
0x14003bbb1  test    r14d, r14d
0x14003bbb4  jz      loc_14003BC68
0x14003bbba  mov     rax, [rsp+88h+bstrString]
0x14003bbc2  test    rax, rax
0x14003bbc5  jz      short loc_14003BBDE
0x14003bbc7  mov     rcx, rax; bstrString
0x14003bbca  call    cs:__imp_SysFreeString
0x14003bbd1  nop     dword ptr [rax+rax+00h]
0x14003bbd6  mov     [rsp+88h+bstrString], r13
0x14003bbde  mov     rcx, [rdi+170h]
0x14003bbe5  test    rcx, rcx
0x14003bbe8  cmovz   rcx, r13
0x14003bbec  movsxd  rax, esi
0x14003bbef  mov     rcx, [rcx+rax*8]
0x14003bbf3  mov     rax, [rcx]
0x14003bbf6  lea     rdx, [rsp+88h+bstrString]
0x14003bbfe  mov     rax, [rax+20h]
0x14003bc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bc07  mov     ebx, eax
0x14003bc09  cmp     eax, 80070490h
0x14003bc0e  jnz     short loc_14003BC15
0x14003bc10  mov     ebx, r13d
0x14003bc13  jmp     short loc_14003BC1D
0x14003bc15  test    ebx, ebx
0x14003bc17  js      loc_14003BD05
0x14003bc1d  mov     rax, [rsp+88h+bstrString]
0x14003bc25  test    rax, rax
0x14003bc28  jz      short loc_14003BC5D
0x14003bc2a  or      ecx, 0FFFFFFFFh
0x14003bc2d  mov     dword ptr [rsp+88h+cchCount2], ecx; cchCount2
0x14003bc31  mov     [rsp+88h+lpString2], rax; lpString2
0x14003bc36  mov     r9d, ecx; cchCount1
0x14003bc39  mov     r8, rbp; lpString1
0x14003bc3c  lea     edx, [rcx+2]; dwCmpFlags
0x14003bc3f  mov     ecx, 409h; Locale
0x14003bc44  call    cs:__imp_CompareStringW
0x14003bc4b  nop     dword ptr [rax+rax+00h]
0x14003bc50  cmp     eax, 2
0x14003bc53  jz      short loc_14003BCD2
0x14003bc55  mov     rax, [rsp+88h+bstrString]
0x14003bc5d  inc     esi
0x14003bc5f  cmp     esi, r14d
0x14003bc62  jb      loc_14003BBC2
0x14003bc68  mov     ebx, 80070490h
0x14003bc6d  mov     ecx, ebx
0x14003bc6f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003bc74  mov     rcx, [rsp+88h+bstrString]; bstrString
0x14003bc7c  test    rcx, rcx
0x14003bc7f  jz      short loc_14003BC95
0x14003bc81  call    cs:__imp_SysFreeString
0x14003bc88  nop     dword ptr [rax+rax+00h]
0x14003bc8d  mov     [rsp+88h+bstrString], r13
0x14003bc95  mov     eax, [rsp+88h+var_40]
0x14003bc99  test    eax, eax
0x14003bc9b  jz      short loc_14003BCB1
0x14003bc9d  mov     rcx, r12; lpCriticalSection
0x14003bca0  call    cs:__imp_LeaveCriticalSection
0x14003bca7  nop     dword ptr [rax+rax+00h]
0x14003bcac  mov     [rsp+88h+var_40], r13d
0x14003bcb1  mov     eax, ebx
0x14003bcb3  lea     r11, [rsp+88h+var_28]
0x14003bcb8  mov     rbx, [r11+38h]
0x14003bcbc  mov     rbp, [r11+40h]
0x14003bcc0  mov     rsi, [r11+48h]
0x14003bcc4  mov     rsp, r11
0x14003bcc7  pop     r15
0x14003bcc9  pop     r14
0x14003bccb  pop     r13
0x14003bccd  pop     r12
0x14003bccf  pop     rdi
0x14003bcd0  retn
0x14003bcd2  lfence
0x14003bcd5  mov     rcx, [rdi+170h]
0x14003bcdc  test    rcx, rcx
0x14003bcdf  cmovz   rcx, r13
0x14003bce3  movsxd  rax, esi
0x14003bce6  mov     rcx, [rcx+rax*8]
0x14003bcea  test    rcx, rcx
0x14003bced  cmovz   rcx, r13
0x14003bcf1  mov     [r15], rcx
0x14003bcf4  mov     rax, [rcx]
0x14003bcf7  mov     rax, [rax+8]
0x14003bcfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bd00  jmp     loc_14003BC6D
0x14003bd05  mov     rax, [rdi+0B0h]
0x14003bd0c  lea     rcx, [rdi+0B0h]
0x14003bd13  mov     rax, [rax+10h]
0x14003bd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bd1c  test    rax, rax
0x14003bd1f  jz      loc_14003BC6D
0x14003bd25  mov     rax, [rdi+0B0h]
0x14003bd2c  lea     rcx, [rdi+0B0h]
0x14003bd33  mov     rax, [rax+10h]
0x14003bd37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bd3c  mov     edi, r13d
0x14003bd3f  test    rax, rax
0x14003bd42  jz      loc_14003BA79
0x14003bd48  mov     dword ptr [rsp+88h+cchCount2], ebx
0x14003bd4c  mov     dword ptr [rsp+88h+lpString2], 750h
0x14003bd54  jmp     loc_14003BA51
```
