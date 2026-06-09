# TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)

- ea: `0x180017d2c`
- end: `0x180017dd6`
- name: `??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z`
- size: `170`
- prototype: `__int64 __fastcall(HMODULE, __int64, __int64, void *, int, void **Src)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b400`
- `0x18000c394`
- `0x18000c754`
- `0x18000c870`

## callees

- `0x180017d2c`
- `0x180017ddc`
- `0x180017e0c`
- `0x18002295c`

## pseudocode

```c
__int64 __fastcall TResourceStringAllocCopyEx<unsigned short *>(
        HMODULE a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        int a5,
        void **Src)
{
  void **v6; // rsi
  int v7; // ebx
  size_t v8; // rdi
  unsigned __int16 v10; // [rsp+50h] [rbp+18h] BYREF
  void *v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = a4;
  v6 = Src;
  Src = 0;
  v10 = 0;
  *v6 = 0;
  v7 = ResourceStringFindAndSizeEx(a1, (__int64)&v10);
  if ( v7 >= 0 )
  {
    v11 = 0;
    v8 = 2LL * v10;
    v7 = ResourceStringAllocCopyExCoAlloc(0, v8 + 2, &v11);
    if ( v7 >= 0 )
    {
      memcpy_0(v11, Src, v8);
      *(_WORD *)((char *)v11 + v8) = 0;
      *v6 = v11;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017d2c  mov     r11, rsp
0x180017d2f  mov     [r11+8], rbx
0x180017d33  mov     [r11+10h], rsi
0x180017d37  mov     [r11+20h], r9
0x180017d3b  mov     [r11+18h], r8w
0x180017d40  push    rdi
0x180017d41  sub     rsp, 30h
0x180017d45  mov     rsi, [rsp+38h+Src]
0x180017d4a  lea     r9, [r11+30h]
0x180017d4e  xor     eax, eax
0x180017d50  mov     qword ptr [r11+30h], 0
0x180017d58  mov     [rsp+38h+arg_10], ax
0x180017d5d  lea     rax, [r11+18h]
0x180017d61  mov     [r11-18h], rax
0x180017d65  mov     qword ptr [rsi], 0
0x180017d6c  call    ResourceStringFindAndSizeEx
0x180017d71  mov     ebx, eax
0x180017d73  test    eax, eax
0x180017d75  js      short loc_180017DC4
0x180017d77  movzx   eax, [rsp+38h+arg_10]
0x180017d7c  lea     r8, [rsp+38h+arg_18]
0x180017d81  xor     ecx, ecx
0x180017d83  mov     [rsp+38h+arg_18], 0
0x180017d8c  lea     rdi, [rax+rax]
0x180017d90  lea     rdx, [rdi+2]
0x180017d94  call    _ResourceStringAllocCopyExCoAlloc
0x180017d99  mov     ebx, eax
0x180017d9b  test    eax, eax
0x180017d9d  js      short loc_180017DC4
0x180017d9f  mov     rdx, [rsp+38h+Src]; Src
0x180017da4  mov     r8, rdi; Size
0x180017da7  mov     rcx, [rsp+38h+arg_18]; void *
0x180017dac  call    memcpy_0
0x180017db1  mov     rax, [rsp+38h+arg_18]
0x180017db6  xor     ecx, ecx
0x180017db8  mov     [rdi+rax], cx
0x180017dbc  mov     rax, [rsp+38h+arg_18]
0x180017dc1  mov     [rsi], rax
0x180017dc4  mov     rsi, [rsp+38h+arg_8]
0x180017dc9  mov     eax, ebx
0x180017dcb  mov     rbx, [rsp+38h+arg_0]
0x180017dd0  add     rsp, 30h
0x180017dd4  pop     rdi
0x180017dd5  retn
```
