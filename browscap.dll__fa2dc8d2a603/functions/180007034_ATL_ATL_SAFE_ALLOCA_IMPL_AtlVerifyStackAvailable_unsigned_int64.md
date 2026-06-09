# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x180007034`
- end: `0x1800070b7`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `131`
- prototype: `bool __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *__hidden this, unsigned __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b10`
- `0x180002cc8`
- `0x180002e4c`
- `0x180003f7c`
- `0x1800050c0`
- `0x180005d94`
- `0x180005eb0`
- `0x1800060d0`
- `0x1800061ec`
- `0x18000672c`
- `0x180006b14`

## callees

- `0x180007034`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180007098`
- `msvcrt!_resetstkoflw` at `0x180007098`

## pseudocode

```c
char __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64 this)
{
  char v1; // bl
  char *v2; // rax
  unsigned __int64 v3; // rcx
  void *v4; // rsp
  void *v5; // rsp

  v1 = 1;
  if ( ~this < 0x4000 )
    return 0;
  v2 = (char *)(this + 0x4000);
  v3 = this + 16399;
  if ( v3 <= (unsigned __int64)v2 )
    v3 = 0xFFFFFFFFFFFFFF0LL;
  v4 = alloca(v3 & 0xFFFFFFFFFFFFFFF0uLL);
  v5 = alloca(v3 & 0xFFFFFFFFFFFFFFF0uLL);
  return v1;
}

```

## disassembly

```asm
0x180007034  push    rbp
0x180007036  sub     rsp, 30h
0x18000703a  lea     rbp, [rsp+20h]
0x18000703f  mov     [rbp+10h+arg_0], rbx
0x180007043  mov     rax, cs:__security_cookie
0x18000704a  xor     rax, rbp
0x18000704d  mov     [rbp+10h+var_8], rax
0x180007051  mov     bl, 1
0x180007053  mov     rax, rcx
0x180007056  not     rax
0x180007059  cmp     rax, 4000h
0x18000705f  jb      short loc_18000708C
0x180007061  lea     rax, [rcx+4000h]
0x180007068  lea     rcx, [rax+0Fh]
0x18000706c  cmp     rcx, rax
0x18000706f  ja      short loc_18000707B
0x180007071  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000707b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000707f  mov     rax, rcx
0x180007082  call    _alloca_probe
0x180007087  sub     rsp, rcx
0x18000708a  jmp     short loc_180007091
0x18000708c  xor     bl, bl
0x18000708e  mov     [rbp+10h+var_10], bl
0x180007091  jmp     short loc_18000709F
0x180007093  xor     bl, bl
0x180007095  mov     [rbp+10h+var_10], bl
0x180007098  call    cs:__imp__resetstkoflw
0x18000709e  nop
0x18000709f  mov     al, bl
0x1800070a1  mov     rcx, [rbp+10h+var_8]
0x1800070a5  xor     rcx, rbp; StackCookie
0x1800070a8  call    __security_check_cookie
0x1800070ad  mov     rbx, [rbp+10h+arg_0]
0x1800070b1  lea     rsp, [rbp+10h]
0x1800070b5  pop     rbp
0x1800070b6  retn
0x18000bd08  push    rbp
0x18000bd0a  sub     rsp, 20h
0x18000bd0e  lea     rbp, [rdx+20h]
0x18000bd12  mov     rax, [rcx]
0x18000bd15  xor     ecx, ecx
0x18000bd17  cmp     dword ptr [rax], 0C00000FDh
0x18000bd1d  setz    cl
0x18000bd20  mov     eax, ecx
0x18000bd22  add     rsp, 20h
0x18000bd26  pop     rbp
0x18000bd27  retn
```
