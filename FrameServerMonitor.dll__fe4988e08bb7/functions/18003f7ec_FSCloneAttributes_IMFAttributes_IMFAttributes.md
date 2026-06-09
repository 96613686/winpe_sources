# FSCloneAttributes(IMFAttributes *,IMFAttributes * *)

- ea: `0x18003f7ec`
- end: `0x18003f901`
- name: `?FSCloneAttributes@@YAJPEAUIMFAttributes@@PEAPEAU1@@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct IMFAttributes *, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023b24`

## callees

- `0x180005f98`
- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x18003f7ec`
- `0x18004d010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18003f883`
- `MFPlat!MFCreateAttributes` at `0x18003f883`

## pseudocode

```c
__int64 __fastcall FSCloneAttributes(struct IMFAttributes *a1, struct IMFAttributes **a2)
{
  UINT32 v2; // ebx
  HRESULT v5; // ebx
  __int64 v6; // rdx
  UINT32 v8; // [rsp+48h] [rbp+10h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v8 = 0;
  ppMFAttributes = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_17;
  }
  *a2 = 0;
  if ( a1 )
  {
    v5 = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))a1->lpVtbl->GetCount)(a1, &v8);
    if ( v5 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_17;
      v6 = 78;
LABEL_7:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v5);
      goto LABEL_17;
    }
    v2 = v8;
  }
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v5 = MFCreateAttributes(&ppMFAttributes, v2);
  if ( v5 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_17;
    v6 = 79;
    goto LABEL_7;
  }
  if ( !a1
    || (v5 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a1->lpVtbl->CopyAllItems)(
               a1,
               ppMFAttributes),
        v5 >= 0) )
  {
    *a2 = ppMFAttributes;
    ppMFAttributes = 0;
    goto LABEL_17;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v6 = 80;
    goto LABEL_7;
  }
LABEL_17:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003f7ec  mov     rax, rsp
0x18003f7ef  mov     [rax+8], rbx
0x18003f7f3  mov     [rax+20h], rsi
0x18003f7f7  push    rdi
0x18003f7f8  sub     rsp, 30h
0x18003f7fc  xor     ebx, ebx
0x18003f7fe  mov     rsi, rdx
0x18003f801  mov     [rax+10h], ebx
0x18003f804  mov     rdi, rcx
0x18003f807  mov     [rax+18h], rbx
0x18003f80b  test    rdx, rdx
0x18003f80e  jnz     short loc_18003F81A
0x18003f810  mov     ebx, 80004003h
0x18003f815  jmp     loc_18003F8E5
0x18003f81a  mov     [rdx], rbx
0x18003f81d  test    rdi, rdi
0x18003f820  jz      short loc_18003F872
0x18003f822  mov     rax, [rcx]
0x18003f825  lea     rdx, [rsp+38h+arg_8]
0x18003f82a  mov     rax, [rax+0F0h]
0x18003f831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f836  mov     ebx, eax
0x18003f838  test    eax, eax
0x18003f83a  jns     short loc_18003F86E
0x18003f83c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003f841  cmp     al, 1
0x18003f843  jb      loc_18003F8E5
0x18003f849  mov     edx, 4Eh ; 'N'
0x18003f84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f855  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18003f85c  xor     r9d, r9d
0x18003f85f  mov     [rsp+38h+var_18], ebx
0x18003f863  mov     rcx, [rcx+10h]
0x18003f867  call    WPP_SF_qD
0x18003f86c  jmp     short loc_18003F8E5
0x18003f86e  mov     ebx, [rsp+38h+arg_8]
0x18003f872  lea     rcx, [rsp+38h+ppMFAttributes]
0x18003f877  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003f87c  mov     edx, ebx; cInitialSize
0x18003f87e  lea     rcx, [rsp+38h+ppMFAttributes]; ppMFAttributes
0x18003f883  call    cs:__imp_MFCreateAttributes
0x18003f889  mov     ebx, eax
0x18003f88b  test    eax, eax
0x18003f88d  jns     short loc_18003F89F
0x18003f88f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003f894  cmp     al, 1
0x18003f896  jb      short loc_18003F8E5
0x18003f898  mov     edx, 4Fh ; 'O'
0x18003f89d  jmp     short loc_18003F84E
0x18003f89f  test    rdi, rdi
0x18003f8a2  jz      short loc_18003F8D4
0x18003f8a4  mov     rax, [rdi]
0x18003f8a7  mov     rcx, rdi
0x18003f8aa  mov     rdx, [rsp+38h+ppMFAttributes]
0x18003f8af  mov     rax, [rax+100h]
0x18003f8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8bb  mov     ebx, eax
0x18003f8bd  test    eax, eax
0x18003f8bf  jns     short loc_18003F8D4
0x18003f8c1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003f8c6  cmp     al, 1
0x18003f8c8  jb      short loc_18003F8E5
0x18003f8ca  mov     edx, 50h ; 'P'
0x18003f8cf  jmp     loc_18003F84E
0x18003f8d4  mov     rax, [rsp+38h+ppMFAttributes]
0x18003f8d9  mov     [rsi], rax
0x18003f8dc  mov     [rsp+38h+ppMFAttributes], 0
0x18003f8e5  lea     rcx, [rsp+38h+ppMFAttributes]
0x18003f8ea  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003f8ef  mov     rsi, [rsp+38h+arg_18]
0x18003f8f4  mov     eax, ebx
0x18003f8f6  mov     rbx, [rsp+38h+arg_0]
0x18003f8fb  add     rsp, 30h
0x18003f8ff  pop     rdi
0x18003f900  retn
```
