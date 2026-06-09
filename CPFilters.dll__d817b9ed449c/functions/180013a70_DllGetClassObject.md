# DllGetClassObject

- ea: `0x180013a70`
- end: `0x180013b59`
- name: `DllGetClassObject`
- size: `233`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e60`
- `0x180013a70`
- `0x18006cc58`
- `0x18006ccc0`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v7; // ebx
  wchar_t **v8; // rsi
  _QWORD *v9; // rax

  *ppv = 0;
  if ( memcmp(riid, &qword_180075658, 0x10u) && memcmp(riid, &qword_180075668, 0x10u) )
    return -2147467262;
  v7 = 0;
  while ( 1 )
  {
    v8 = &(&off_180088000)[5 * v7];
    if ( !memcmp(v8[1], rclsid, 0x10u) )
      break;
    if ( ++v7 >= 3 )
      return -2147221231;
  }
  v9 = (_QWORD *)sub_180001E60(24);
  if ( v9 )
  {
    _InterlockedIncrement(&dword_180089860);
    v9[1] = v8;
    *v9 = off_180070130;
    *((_DWORD *)v9 + 4) = 0;
    *ppv = v9;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    return 0;
  }
  else
  {
    *ppv = 0;
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180013a70  push    rbx
0x180013a72  push    rbp
0x180013a73  push    rsi
0x180013a74  push    rdi
0x180013a75  push    r15
0x180013a77  sub     rsp, 20h
0x180013a7b  mov     rbx, rdx
0x180013a7e  mov     qword ptr [r8], 0
0x180013a85  mov     rdi, r8
0x180013a88  lea     rdx, qword_180075658; Buf2
0x180013a8f  mov     rbp, rcx
0x180013a92  mov     r15d, 10h
0x180013a98  mov     r8d, r15d; Size
0x180013a9b  mov     rcx, rbx; Buf1
0x180013a9e  call    memcmp
0x180013aa3  test    eax, eax
0x180013aa5  jz      short loc_180013AC7
0x180013aa7  mov     r8d, r15d; Size
0x180013aaa  lea     rdx, qword_180075668; Buf2
0x180013ab1  mov     rcx, rbx; Buf1
0x180013ab4  call    memcmp
0x180013ab9  test    eax, eax
0x180013abb  jz      short loc_180013AC7
0x180013abd  mov     eax, 80004002h
0x180013ac2  jmp     loc_180013B4D
0x180013ac7  xor     ebx, ebx
0x180013ac9  movsxd  rax, ebx
0x180013acc  mov     r8, r15; Size
0x180013acf  mov     rdx, rbp; Buf2
0x180013ad2  lea     rcx, [rax+rax*4]
0x180013ad6  lea     rax, off_180088000; "PBDA PTFilter"
0x180013add  lea     rsi, [rax+rcx*8]
0x180013ae1  mov     rcx, [rsi+8]; Buf1
0x180013ae5  call    memcmp
0x180013aea  test    eax, eax
0x180013aec  jz      short loc_180013AFC
0x180013aee  inc     ebx
0x180013af0  cmp     ebx, 3
0x180013af3  jl      short loc_180013AC9
0x180013af5  mov     eax, 80040111h
0x180013afa  jmp     short loc_180013B4D
0x180013afc  mov     ecx, 18h
0x180013b01  call    sub_180001E60
0x180013b06  mov     rdx, rax
0x180013b09  test    rax, rax
0x180013b0c  jz      short loc_180013B41
0x180013b0e  lock inc cs:dword_180089860
0x180013b15  mov     [rdx+8], rsi
0x180013b19  lea     rax, off_180070130
0x180013b20  mov     [rdx], rax
0x180013b23  mov     dword ptr [rdx+10h], 0
0x180013b2a  mov     [rdi], rdx
0x180013b2d  mov     rcx, [rdx]
0x180013b30  mov     rax, [rcx+8]
0x180013b34  mov     rcx, rdx
0x180013b37  call    cs:__guard_dispatch_icall_fptr
0x180013b3d  xor     eax, eax
0x180013b3f  jmp     short loc_180013B4D
0x180013b41  mov     qword ptr [rdi], 0
0x180013b48  mov     eax, 8007000Eh
0x180013b4d  add     rsp, 20h
0x180013b51  pop     r15
0x180013b53  pop     rdi
0x180013b54  pop     rsi
0x180013b55  pop     rbp
0x180013b56  pop     rbx
0x180013b57  retn
```
