# _lambda_374e7b5dfa3a81f16edfaa5e4ee1837e_::operator()

- ea: `0x180012eac`
- end: `0x180012f5c`
- name: `_lambda_374e7b5dfa3a81f16edfaa5e4ee1837e_::operator()`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012760`

## callees

- `0x180010670`
- `0x180012d88`
- `0x180012eac`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ee3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ee3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_374e7b5dfa3a81f16edfaa5e4ee1837e_::operator()(__int64 a1)
{
  char v2; // bl
  int v3; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v7; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v2 = 1;
  CoCreateInstance(&GUID_7da2a2ba_8276_4738_94eb_97ffaaa559ca, 0, 1u, &GUID_25cde345_19f3_4b67_849b_65b93f60bb4b, &v8);
  v7 = 0;
  if ( !v8 )
    goto LABEL_5;
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, int *))(*(_QWORD *)v8 + 24LL))(
         v8,
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         L"ID_CAP_PUBLIC_FOLDER_FULL",
         &v7);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x102,
      (int)"onecore\\base\\windows.storage\\src\\identity.cpp",
      (const char *)(unsigned int)v3,
      v5);
  if ( !v7 )
LABEL_5:
    v2 = 0;
  *(_BYTE *)(*(_QWORD *)a1 + 56LL) = v2;
  return wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>((__int64 *)&v8);
}

```

## disassembly

```asm
0x180012eac  mov     r11, rsp
0x180012eaf  mov     [r11+8], rbx
0x180012eb3  push    rdi
0x180012eb4  sub     rsp, 30h
0x180012eb8  mov     rdi, rcx
0x180012ebb  mov     qword ptr [r11+18h], 0
0x180012ec3  lea     rax, [r11+18h]
0x180012ec7  mov     [r11-18h], rax
0x180012ecb  lea     r9, _GUID_25cde345_19f3_4b67_849b_65b93f60bb4b; riid
0x180012ed2  mov     ebx, 1
0x180012ed7  mov     r8d, ebx; dwClsContext
0x180012eda  xor     edx, edx; pUnkOuter
0x180012edc  lea     rcx, _GUID_7da2a2ba_8276_4738_94eb_97ffaaa559ca; rclsid
0x180012ee3  call    cs:__imp_CoCreateInstance
0x180012ee9  mov     [rsp+38h+arg_8], 0
0x180012ef1  mov     rcx, [rsp+38h+arg_10]
0x180012ef6  test    rcx, rcx
0x180012ef9  jz      short loc_180012F3F
0x180012efb  mov     rax, [rcx]
0x180012efe  mov     rdx, [rdi]
0x180012f01  lea     r9, [rsp+38h+arg_8]
0x180012f06  lea     r8, aIdCapPublicFol; "ID_CAP_PUBLIC_FOLDER_FULL"
0x180012f0d  mov     rdx, [rdx+8]
0x180012f11  mov     rax, [rax+18h]
0x180012f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f1a  mov     rcx, [rsp+38h]; this
0x180012f1f  test    eax, eax
0x180012f21  jns     short loc_180012F38
0x180012f23  mov     r9d, eax; char *
0x180012f26  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\windows.storage\\src\\id"...
0x180012f2d  mov     edx, 102h; void *
0x180012f32  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012f38  cmp     [rsp+38h+arg_8], 0
0x180012f3d  jnz     short loc_180012F41
0x180012f3f  xor     bl, bl
0x180012f41  mov     rax, [rdi]
0x180012f44  mov     [rax+38h], bl
0x180012f47  lea     rcx, [rsp+38h+arg_10]
0x180012f4c  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x180012f51  mov     rbx, [rsp+38h+arg_0]
0x180012f56  add     rsp, 30h
0x180012f5a  pop     rdi
0x180012f5b  retn
```
