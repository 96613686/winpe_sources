# RegisterPackageDependency(winrt::hstring)

- ea: `0x18001a388`
- end: `0x18001a49c`
- name: `?RegisterPackageDependency@@YAJUhstring@winrt@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013928`

## callees

- `0x180005eac`
- `0x18000972c`
- `0x180012748`
- `0x18001a388`
- `0x18001d518`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x18001a42c`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x18001a42c`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18001a3f6`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18001a3f6`

## string_xrefs

- `0x18001a444`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall RegisterPackageDependency(__int64 *a1)
{
  __int64 v1; // rax
  char *v3; // rdx
  int PackageDependency; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  void *v8; // rdx
  void *v9; // rdx
  wil::details *v10; // rcx
  wil::details *v11; // rcx
  _QWORD v13[2]; // [rsp+40h] [rbp-20h] BYREF
  char v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  wil::details *v16; // [rsp+70h] [rbp+10h] BYREF
  __int64 v17; // [rsp+78h] [rbp+18h] BYREF

  v17 = 0;
  v13[0] = &v16;
  v1 = *a1;
  v16 = 0;
  v13[1] = 0;
  v14 = 1;
  if ( v1 )
    v3 = *(char **)(v1 + 16);
  else
    v3 = byte_180026660;
  PackageDependency = TryCreatePackageDependency(0, v3, 0, 0);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>(v13);
  if ( PackageDependency < 0 )
  {
    v5 = (unsigned int)PackageDependency;
    v6 = 180;
    goto LABEL_8;
  }
  v7 = AddPackageDependency(v16, 0, 1, &v17);
  PackageDependency = v7;
  if ( v7 < 0 )
  {
    v5 = (unsigned int)v7;
    v6 = 187;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
      (const char *)v5,
      0);
    v10 = v16;
    v16 = 0;
    if ( v10 )
      wil::details::FreeProcessHeap(v10, v9);
    goto LABEL_13;
  }
  v11 = v16;
  v16 = 0;
  if ( v11 )
    wil::details::FreeProcessHeap(v11, v8);
  PackageDependency = 0;
LABEL_13:
  winrt::handle_type<winrt::impl::hstring_traits>::close(a1);
  return (unsigned int)PackageDependency;
}

```

## disassembly

```asm
0x18001a388  mov     [rsp-8+arg_10], rbx
0x18001a38d  mov     [rsp-8+arg_18], rdi
0x18001a392  push    rbp
0x18001a393  mov     rbp, rsp
0x18001a396  sub     rsp, 60h
0x18001a39a  lea     rax, [rbp+arg_0]
0x18001a39e  mov     [rbp+arg_8], 0
0x18001a3a6  mov     [rbp+var_20], rax
0x18001a3aa  xor     r8d, r8d
0x18001a3ad  mov     rax, [rcx]
0x18001a3b0  mov     rdi, rcx
0x18001a3b3  mov     [rbp+arg_0], 0
0x18001a3bb  mov     [rbp+var_18], 0
0x18001a3c3  mov     [rbp+var_10], 1
0x18001a3c7  test    rax, rax
0x18001a3ca  jz      short loc_18001A3D2
0x18001a3cc  mov     rdx, [rax+10h]
0x18001a3d0  jmp     short loc_18001A3D9
0x18001a3d2  lea     rdx, byte_180026660
0x18001a3d9  lea     rax, [rbp+var_18]
0x18001a3dd  xor     r9d, r9d
0x18001a3e0  mov     [rsp+60h+var_28], rax
0x18001a3e5  xor     ecx, ecx
0x18001a3e7  mov     [rsp+60h+var_30], r8d
0x18001a3ec  mov     [rsp+60h+var_38], r8
0x18001a3f1  mov     [rsp+60h+var_40], r8d
0x18001a3f6  call    cs:__imp_TryCreatePackageDependency
0x18001a3fc  lea     rcx, [rbp+var_20]
0x18001a400  mov     ebx, eax
0x18001a402  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>(void)
0x18001a407  test    ebx, ebx
0x18001a409  jns     short loc_18001A415
0x18001a40b  mov     r9d, ebx
0x18001a40e  mov     edx, 0B4h
0x18001a413  jmp     short loc_18001A440
0x18001a415  mov     rcx, [rbp+arg_0]
0x18001a419  lea     r9, [rbp+arg_8]
0x18001a41d  xor     edx, edx
0x18001a41f  mov     qword ptr [rsp+60h+var_40], 0; int
0x18001a428  lea     r8d, [rdx+1]
0x18001a42c  call    cs:__imp_AddPackageDependency
0x18001a432  mov     ebx, eax
0x18001a434  test    eax, eax
0x18001a436  jns     short loc_18001A468
0x18001a438  mov     r9d, eax; char *
0x18001a43b  mov     edx, 0BBh; void *
0x18001a440  mov     rcx, [rbp+8]; this
0x18001a444  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001a44b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a450  mov     rcx, [rbp+arg_0]; this
0x18001a454  mov     [rbp+arg_0], 0
0x18001a45c  test    rcx, rcx
0x18001a45f  jz      short loc_18001A480
0x18001a461  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001a466  jmp     short loc_18001A480
0x18001a468  mov     rcx, [rbp+arg_0]; this
0x18001a46c  mov     [rbp+arg_0], 0
0x18001a474  test    rcx, rcx
0x18001a477  jz      short loc_18001A47E
0x18001a479  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001a47e  xor     ebx, ebx
0x18001a480  mov     rcx, rdi
0x18001a483  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001a488  lea     r11, [rsp+60h+var_s0]
0x18001a48d  mov     eax, ebx
0x18001a48f  mov     rbx, [r11+20h]
0x18001a493  mov     rdi, [r11+28h]
0x18001a497  mov     rsp, r11
0x18001a49a  pop     rbp
0x18001a49b  retn
```
