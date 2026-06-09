# TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)

- ea: `0x180009800`
- end: `0x1800098aa`
- name: `??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z`
- size: `170`
- prototype: `__int64 __fastcall(HMODULE, __int64, __int64, void *, int, void **Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008100`
- `0x1800085e8`
- `0x18000995c`

## callees

- `0x180009800`
- `0x180009900`
- `0x180009a48`
- `0x18000b6d2`

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
    v7 = ResourceStringAllocCopyExLocalAlloc(0, v8 + 2, &v11);
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
0x180009800  mov     r11, rsp
0x180009803  mov     [r11+8], rbx
0x180009807  mov     [r11+10h], rsi
0x18000980b  mov     [r11+20h], r9
0x18000980f  mov     [r11+18h], r8w
0x180009814  push    rdi
0x180009815  sub     rsp, 30h
0x180009819  mov     rsi, [rsp+38h+Src]
0x18000981e  lea     r9, [r11+30h]
0x180009822  xor     eax, eax
0x180009824  mov     qword ptr [r11+30h], 0
0x18000982c  mov     [rsp+38h+arg_10], ax
0x180009831  lea     rax, [r11+18h]
0x180009835  mov     [r11-18h], rax
0x180009839  mov     qword ptr [rsi], 0
0x180009840  call    ResourceStringFindAndSizeEx
0x180009845  mov     ebx, eax
0x180009847  test    eax, eax
0x180009849  js      short loc_180009898
0x18000984b  movzx   eax, [rsp+38h+arg_10]
0x180009850  lea     r8, [rsp+38h+arg_18]
0x180009855  xor     ecx, ecx
0x180009857  mov     [rsp+38h+arg_18], 0
0x180009860  lea     rdi, [rax+rax]
0x180009864  lea     rdx, [rdi+2]
0x180009868  call    _ResourceStringAllocCopyExLocalAlloc
0x18000986d  mov     ebx, eax
0x18000986f  test    eax, eax
0x180009871  js      short loc_180009898
0x180009873  mov     rdx, [rsp+38h+Src]; Src
0x180009878  mov     r8, rdi; Size
0x18000987b  mov     rcx, [rsp+38h+arg_18]; void *
0x180009880  call    memcpy_0
0x180009885  mov     rax, [rsp+38h+arg_18]
0x18000988a  xor     ecx, ecx
0x18000988c  mov     [rdi+rax], cx
0x180009890  mov     rax, [rsp+38h+arg_18]
0x180009895  mov     [rsi], rax
0x180009898  mov     rsi, [rsp+38h+arg_8]
0x18000989d  mov     eax, ebx
0x18000989f  mov     rbx, [rsp+38h+arg_0]
0x1800098a4  add     rsp, 30h
0x1800098a8  pop     rdi
0x1800098a9  retn
```
