# Windows::Internal::SyncRootHelpers::PerformCloudFilePinAction(HWND__ *,IShellItemArray *,CloudFilePinAction)

- ea: `0x1800759e4`
- end: `0x180075be4`
- name: `?PerformCloudFilePinAction@SyncRootHelpers@Internal@Windows@@YAJPEAUHWND__@@PEAUIShellItemArray@@W4CloudFilePinAction@@@Z`
- size: `512`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800287d0`
- `0x18003c740`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x1800759e4`
- `0x1800769ac`
- `0x180089010`

## import_xrefs

- `PROPSYS!PSCreateSimplePropertyChange` at `0x180075ab3`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x180075ab3`
- `PROPSYS!PSCreatePropertyChangeArray` at `0x180075a32`
- `PROPSYS!PSCreatePropertyChangeArray` at `0x180075a32`

## string_xrefs

- `0x180075a45`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootverbs.cpp`
- `0x180075ac4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootverbs.cpp`
- `0x180075b2f`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootverbs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::SyncRootHelpers::PerformCloudFilePinAction(HWND a1, __int64 a2, int a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // edx
  const struct _GUID *v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  int riid; // [rsp+20h] [rbp-40h]
  int riida; // [rsp+20h] [rbp-40h]
  void *v18; // [rsp+30h] [rbp-30h] BYREF
  void *ppv; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT propvar; // [rsp+40h] [rbp-20h] BYREF
  int v21; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *v23; // [rsp+98h] [rbp+38h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
  v6 = PSCreatePropertyChangeArray(0, 0, 0, 0, &GUID_380f5cad_1b5e_42f2_805d_637fd392d31e, &ppv);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v18 = 0;
    v8 = 1;
    if ( a3 != 1 )
    {
      if ( a3 == 2 )
      {
        v8 = 12;
      }
      else
      {
        v8 = 0;
        if ( a3 == 3 )
          v8 = 14;
      }
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
    LOWORD(propvar) = 19;
    v21 = v8;
    v9 = PSCreateSimplePropertyChange(
           PKA_SET,
           &PKEY_FilePlaceholderStatus,
           &propvar,
           &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431,
           &v18);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)ppv + 48LL))(ppv, v18);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v23 = 0;
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
        v13 = SHCreateFileOperation(a1, v11, v12, &v23);
        v7 = v13;
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(void *, void *))(*(_QWORD *)v23 + 64LL))(v23, ppv);
          v7 = v13;
          if ( v13 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v23 + 88LL))(v23, a2);
            v7 = v13;
            if ( v13 >= 0 )
            {
              v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 168LL))(v23);
              v7 = v13;
              if ( v13 >= 0 )
              {
                Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
                Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
                v7 = 0;
                goto LABEL_24;
              }
              v14 = 222;
            }
            else
            {
              v14 = 221;
            }
          }
          else
          {
            v14 = 220;
          }
        }
        else
        {
          v14 = 219;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootverbs.cpp",
          (const char *)(unsigned int)v13,
          riida);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
        goto LABEL_11;
      }
      v10 = 216;
    }
    else
    {
      v10 = 215;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootverbs.cpp",
      (const char *)(unsigned int)v9,
      riida);
LABEL_11:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC2,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootverbs.cpp",
    (const char *)(unsigned int)v6,
    riid);
LABEL_24:
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
  return v7;
}

```

## disassembly

```asm
0x1800759e4  mov     [rsp-18h+arg_0], rbx
0x1800759e9  mov     [rsp-18h+arg_8], rsi
0x1800759ee  push    rbp
0x1800759ef  push    rdi
0x1800759f0  push    r14
0x1800759f2  mov     rbp, rsp
0x1800759f5  sub     rsp, 60h
0x1800759f9  mov     edi, r8d
0x1800759fc  mov     r14, rdx
0x1800759ff  mov     rsi, rcx
0x180075a02  mov     [rbp+var_28], 0
0x180075a0a  lea     rcx, [rbp+var_28]
0x180075a0e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075a13  lea     rax, [rbp+var_28]
0x180075a17  mov     [rsp+60h+ppv], rax; ppv
0x180075a1c  lea     rax, _GUID_380f5cad_1b5e_42f2_805d_637fd392d31e
0x180075a23  mov     [rsp+60h+riid], rax; int
0x180075a28  xor     r9d, r9d; cChanges
0x180075a2b  xor     r8d, r8d; rgpropvar
0x180075a2e  xor     edx, edx; rgflags
0x180075a30  xor     ecx, ecx; rgpropkey
0x180075a32  call    cs:__imp_PSCreatePropertyChangeArray
0x180075a38  mov     ebx, eax
0x180075a3a  test    eax, eax
0x180075a3c  jns     short loc_180075A5B
0x180075a3e  mov     rcx, [rbp+18h]; this
0x180075a42  mov     r9d, eax; char *
0x180075a45  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\fileexplorer\\windo"...
0x180075a4c  mov     edx, 0C2h; void *
0x180075a51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075a56  jmp     loc_180075BC4
0x180075a5b  mov     [rbp+var_30], 0
0x180075a63  mov     ebx, 1
0x180075a68  cmp     edi, ebx
0x180075a6a  jz      short loc_180075A81
0x180075a6c  cmp     edi, 2
0x180075a6f  jnz     short loc_180075A76
0x180075a71  lea     ebx, [rdi+0Ah]
0x180075a74  jmp     short loc_180075A81
0x180075a76  xor     ebx, ebx
0x180075a78  lea     eax, [rbx+0Eh]
0x180075a7b  cmp     edi, 3
0x180075a7e  cmovz   ebx, eax
0x180075a81  lea     rcx, [rbp+var_30]
0x180075a85  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075a8a  mov     eax, 13h
0x180075a8f  mov     word ptr [rbp+propvar], ax
0x180075a93  mov     [rbp+var_18], ebx
0x180075a96  lea     rax, [rbp+var_30]
0x180075a9a  mov     [rsp+60h+riid], rax; int
0x180075a9f  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x180075aa6  lea     r8, [rbp+propvar]; propvar
0x180075aaa  lea     rdx, PKEY_FilePlaceholderStatus; key
0x180075ab1  xor     ecx, ecx; flags
0x180075ab3  call    cs:__imp_PSCreateSimplePropertyChange
0x180075ab9  mov     ebx, eax
0x180075abb  test    eax, eax
0x180075abd  jns     short loc_180075AE6
0x180075abf  mov     edx, 0D7h; void *
0x180075ac4  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\fileexplorer\\windo"...
0x180075acb  mov     r9d, eax; char *
0x180075ace  mov     rcx, [rbp+18h]; this
0x180075ad2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075ad7  nop
0x180075ad8  lea     rcx, [rbp+var_30]
0x180075adc  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075ae1  jmp     loc_180075BC4
0x180075ae6  mov     rcx, [rbp+var_28]
0x180075aea  mov     rax, [rcx]
0x180075aed  mov     rdx, [rbp+var_30]
0x180075af1  mov     rax, [rax+30h]
0x180075af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075afa  mov     ebx, eax
0x180075afc  test    eax, eax
0x180075afe  jns     short loc_180075B07
0x180075b00  mov     edx, 0D8h
0x180075b05  jmp     short loc_180075AC4
0x180075b07  mov     [rbp+arg_18], 0
0x180075b0f  lea     rcx, [rbp+arg_18]
0x180075b13  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075b18  lea     r9, [rbp+arg_18]; void **
0x180075b1c  mov     rcx, rsi; HWND
0x180075b1f  call    ?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z; SHCreateFileOperation(HWND__ *,ulong,_GUID const &,void * *)
0x180075b24  mov     ebx, eax
0x180075b26  test    eax, eax
0x180075b28  jns     short loc_180075B4E
0x180075b2a  mov     edx, 0DBh; void *
0x180075b2f  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\fileexplorer\\windo"...
0x180075b36  mov     r9d, eax; char *
0x180075b39  mov     rcx, [rbp+18h]; this
0x180075b3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075b42  nop
0x180075b43  lea     rcx, [rbp+arg_18]
0x180075b47  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075b4c  jmp     short loc_180075AD8
0x180075b4e  mov     rcx, [rbp+arg_18]
0x180075b52  mov     rax, [rcx]
0x180075b55  mov     rdx, [rbp+var_28]
0x180075b59  mov     rax, [rax+40h]
0x180075b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b62  mov     ebx, eax
0x180075b64  test    eax, eax
0x180075b66  jns     short loc_180075B6F
0x180075b68  mov     edx, 0DCh
0x180075b6d  jmp     short loc_180075B2F
0x180075b6f  mov     rcx, [rbp+arg_18]
0x180075b73  mov     rax, [rcx]
0x180075b76  mov     rdx, r14
0x180075b79  mov     rax, [rax+58h]
0x180075b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b82  mov     ebx, eax
0x180075b84  test    eax, eax
0x180075b86  jns     short loc_180075B8F
0x180075b88  mov     edx, 0DDh
0x180075b8d  jmp     short loc_180075B2F
0x180075b8f  mov     rcx, [rbp+arg_18]
0x180075b93  mov     rax, [rcx]
0x180075b96  mov     rax, [rax+0A8h]
0x180075b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ba2  mov     ebx, eax
0x180075ba4  test    eax, eax
0x180075ba6  jns     short loc_180075BAF
0x180075ba8  mov     edx, 0DEh
0x180075bad  jmp     short loc_180075B2F
0x180075baf  lea     rcx, [rbp+arg_18]
0x180075bb3  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075bb8  nop
0x180075bb9  lea     rcx, [rbp+var_30]
0x180075bbd  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075bc2  xor     ebx, ebx
0x180075bc4  lea     rcx, [rbp+var_28]
0x180075bc8  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180075bcd  mov     eax, ebx
0x180075bcf  lea     r11, [rsp+60h+var_s0]
0x180075bd4  mov     rbx, [r11+20h]
0x180075bd8  mov     rsi, [r11+28h]
0x180075bdc  mov     rsp, r11
0x180075bdf  pop     r14
0x180075be1  pop     rdi
0x180075be2  pop     rbp
0x180075be3  retn
```
