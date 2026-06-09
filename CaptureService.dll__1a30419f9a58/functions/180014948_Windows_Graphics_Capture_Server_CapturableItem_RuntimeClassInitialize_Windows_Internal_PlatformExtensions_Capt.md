# Windows::Graphics::Capture::Server::CapturableItem::RuntimeClassInitialize(Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool)

- ea: `0x180014948`
- end: `0x1800149ca`
- name: `?RuntimeClassInitialize@CapturableItem@Server@Capture@Graphics@Windows@@QEAAJPEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Z`
- size: `130`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItem *__hidden this, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c3e4`

## callees

- `0x18000907c`
- `0x18000e214`
- `0x180014948`
- `0x180022010`

## string_xrefs

- `0x18001499e`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItem::RuntimeClassInitialize(
        Windows::Graphics::Capture::Server::CapturableItem *this,
        struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *a2,
        char a3)
{
  __int64 (__fastcall *v5)(struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *, _QWORD *); // rbp
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_BYTE *)this + 105) = a3;
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *, _QWORD *))(*(_QWORD *)a2 + 72LL);
  v6 = (_QWORD *)((char *)this + 80);
  v7 = *((_QWORD *)this + 10);
  *v6 = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = v5(a2, v6);
  v9 = v8;
  if ( v8 >= 0 )
  {
    wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::operator=(
      (__int64 *)this + 9,
      (__int64)a2);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v8,
      v11);
    return v9;
  }
}

```

## disassembly

```asm
0x180014948  push    rbx
0x18001494a  push    rbp
0x18001494b  push    rsi
0x18001494c  push    rdi
0x18001494d  sub     rsp, 28h
0x180014951  mov     rdi, rdx
0x180014954  mov     rsi, rcx
0x180014957  mov     [rcx+69h], r8b
0x18001495b  mov     rax, [rdx]
0x18001495e  mov     rbp, [rax+48h]
0x180014962  lea     rbx, [rcx+50h]
0x180014966  mov     rcx, [rbx]
0x180014969  mov     qword ptr [rbx], 0
0x180014970  test    rcx, rcx
0x180014973  jz      short loc_180014982
0x180014975  mov     rax, [rcx]
0x180014978  mov     rax, [rax+10h]
0x18001497c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014981  nop
0x180014982  mov     rdx, rbx
0x180014985  mov     rcx, rdi
0x180014988  mov     rax, rbp
0x18001498b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014990  mov     ebx, eax
0x180014992  test    eax, eax
0x180014994  jns     short loc_1800149B3
0x180014996  mov     rcx, [rsp+48h]; this
0x18001499b  mov     r9d, eax; char *
0x18001499e  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800149a5  mov     edx, 175h; void *
0x1800149aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149af  mov     eax, ebx
0x1800149b1  jmp     short loc_1800149C1
0x1800149b3  lea     rcx, [rsi+48h]
0x1800149b7  mov     rdx, rdi
0x1800149ba  call    ??4?$com_ptr_t@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::operator=(Windows::Internal::PlatformExtensions::Capture::ICapturableItem *)
0x1800149bf  xor     eax, eax
0x1800149c1  add     rsp, 28h
0x1800149c5  pop     rdi
0x1800149c6  pop     rsi
0x1800149c7  pop     rbp
0x1800149c8  pop     rbx
0x1800149c9  retn
```
