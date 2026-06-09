# Windows::Graphics::Capture::Server::DCompManager::Initialize(void)

- ea: `0x18001fd90`
- end: `0x18001fe82`
- name: `?Initialize@DCompManager@Server@Capture@Graphics@Windows@@IEAAJXZ`
- size: `242`
- prototype: `int(Windows::Graphics::Capture::Server::DCompManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fcf4`

## callees

- `0x18000907c`
- `0x18001fd90`
- `0x180022010`

## import_xrefs

- `dcomp!DCompositionCreateDevice` at `0x18001fda9`
- `dcomp!DCompositionCreateDevice` at `0x18001fda9`

## string_xrefs

- `0x18001fdba`: `onecoreuap\windows\dwm\capture\svc\dll\dcompmanager.cpp`
- `0x18001fe60`: `onecoreuap\windows\dwm\capture\svc\dll\dcompmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::DCompManager::Initialize(
        Windows::Graphics::Capture::Server::DCompManager *this)
{
  int Device; // edi
  __int64 v3; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Device = DCompositionCreateDevice(0, &GUID_c37ea93a_e7aa_450d_b16f_9746cb0407f3, this);
  if ( Device < 0 )
  {
    v3 = 36;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\dcompmanager.cpp",
      (const char *)(unsigned int)Device,
      v9);
    return (unsigned int)Device;
  }
  v5 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  Device = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))this)(
             *(_QWORD *)this,
             &GUID_fe1eca1a_bf29_4fb0_9512_03f3e94b431e,
             (char *)this + 8);
  if ( Device < 0 )
  {
    v3 = 39;
    goto LABEL_3;
  }
  v6 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))this)(
         *(_QWORD *)this,
         &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0,
         (char *)this + 16);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\dcompmanager.cpp",
    (const char *)(unsigned int)v7,
    v9);
  return v8;
}

```

## disassembly

```asm
0x18001fd90  mov     [rsp+arg_0], rbx
0x18001fd95  push    rdi; int
0x18001fd96  sub     rsp, 20h
0x18001fd9a  mov     rbx, rcx
0x18001fd9d  mov     r8, rcx
0x18001fda0  lea     rdx, _GUID_c37ea93a_e7aa_450d_b16f_9746cb0407f3
0x18001fda7  xor     ecx, ecx
0x18001fda9  call    cs:__imp_DCompositionCreateDevice
0x18001fdaf  mov     edi, eax
0x18001fdb1  test    eax, eax
0x18001fdb3  jns     short loc_18001FDD5
0x18001fdb5  mov     edx, 24h ; '$'; void *
0x18001fdba  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001fdc1  mov     r9d, edi; char *
0x18001fdc4  mov     rcx, [rsp+28h]; this
0x18001fdc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdce  mov     eax, edi
0x18001fdd0  jmp     loc_18001FE77
0x18001fdd5  lea     rdi, [rbx+8]
0x18001fdd9  mov     rcx, [rdi]
0x18001fddc  mov     qword ptr [rdi], 0
0x18001fde3  test    rcx, rcx
0x18001fde6  jz      short loc_18001FDF5
0x18001fde8  mov     rax, [rcx]
0x18001fdeb  mov     rax, [rax+10h]
0x18001fdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdf4  nop
0x18001fdf5  mov     rcx, [rbx]
0x18001fdf8  mov     rax, [rcx]
0x18001fdfb  mov     r8, rdi
0x18001fdfe  lea     rdx, _GUID_fe1eca1a_bf29_4fb0_9512_03f3e94b431e
0x18001fe05  mov     rax, [rax]
0x18001fe08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe0d  mov     edi, eax
0x18001fe0f  test    eax, eax
0x18001fe11  jns     short loc_18001FE1A
0x18001fe13  mov     edx, 27h ; '''
0x18001fe18  jmp     short loc_18001FDBA
0x18001fe1a  lea     rdi, [rbx+10h]
0x18001fe1e  mov     rcx, [rdi]
0x18001fe21  mov     qword ptr [rdi], 0
0x18001fe28  test    rcx, rcx
0x18001fe2b  jz      short loc_18001FE3A
0x18001fe2d  mov     rax, [rcx]
0x18001fe30  mov     rax, [rax+10h]
0x18001fe34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe39  nop
0x18001fe3a  mov     rcx, [rbx]
0x18001fe3d  mov     rax, [rcx]
0x18001fe40  mov     r8, rdi
0x18001fe43  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x18001fe4a  mov     rax, [rax]
0x18001fe4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe52  mov     ebx, eax
0x18001fe54  test    eax, eax
0x18001fe56  jns     short loc_18001FE75
0x18001fe58  mov     rcx, [rsp+28h]; this
0x18001fe5d  mov     r9d, eax; char *
0x18001fe60  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001fe67  mov     edx, 28h ; '('; void *
0x18001fe6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe71  mov     eax, ebx
0x18001fe73  jmp     short loc_18001FE77
0x18001fe75  xor     eax, eax
0x18001fe77  mov     rbx, [rsp+28h+arg_0]
0x18001fe7c  add     rsp, 20h
0x18001fe80  pop     rdi
0x18001fe81  retn
```
