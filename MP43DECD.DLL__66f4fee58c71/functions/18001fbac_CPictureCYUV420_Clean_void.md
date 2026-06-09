# CPictureCYUV420::Clean(void)

- ea: `0x18001fbac`
- end: `0x18001fc3e`
- name: `?Clean@CPictureCYUV420@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(CPictureCYUV420 *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009ac8`
- `0x180012c74`
- `0x18001fa30`

## callees

- `0x180001420`
- `0x18001fbac`
- `0x18001fd08`

## pseudocode

```c
void __fastcall CPictureCYUV420::Clean(CPictureCYUV420 *this)
{
  void *v1; // rdi
  void *v3; // rdi
  void *v4; // rdi

  v1 = (void *)*((_QWORD *)this + 7);
  if ( v1 )
  {
    CU8Image::~CU8Image(*((CU8Image **)this + 7));
    operator delete(v1);
    *((_QWORD *)this + 7) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    CU8Image::~CU8Image(*((CU8Image **)this + 8));
    operator delete(v3);
    *((_QWORD *)this + 8) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
  {
    CU8Image::~CU8Image(*((CU8Image **)this + 9));
    operator delete(v4);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x18001fbac  mov     [rsp+arg_0], rbx
0x18001fbb1  mov     [rsp+arg_8], rbp
0x18001fbb6  push    rdi
0x18001fbb7  sub     rsp, 20h
0x18001fbbb  mov     rdi, [rcx+38h]
0x18001fbbf  mov     rbx, rcx
0x18001fbc2  mov     ebp, 20h ; ' '
0x18001fbc7  test    rdi, rdi
0x18001fbca  jz      short loc_18001FBE6
0x18001fbcc  mov     rcx, rdi; this
0x18001fbcf  call    ??1CU8Image@@QEAA@XZ; CU8Image::~CU8Image(void)
0x18001fbd4  mov     edx, ebp; unsigned __int64
0x18001fbd6  mov     rcx, rdi; void *
0x18001fbd9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fbde  mov     qword ptr [rbx+38h], 0
0x18001fbe6  mov     rdi, [rbx+40h]
0x18001fbea  test    rdi, rdi
0x18001fbed  jz      short loc_18001FC0A
0x18001fbef  mov     rcx, rdi; this
0x18001fbf2  call    ??1CU8Image@@QEAA@XZ; CU8Image::~CU8Image(void)
0x18001fbf7  mov     rdx, rbp; unsigned __int64
0x18001fbfa  mov     rcx, rdi; void *
0x18001fbfd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fc02  mov     qword ptr [rbx+40h], 0
0x18001fc0a  mov     rdi, [rbx+48h]
0x18001fc0e  test    rdi, rdi
0x18001fc11  jz      short loc_18001FC2E
0x18001fc13  mov     rcx, rdi; this
0x18001fc16  call    ??1CU8Image@@QEAA@XZ; CU8Image::~CU8Image(void)
0x18001fc1b  mov     rdx, rbp; unsigned __int64
0x18001fc1e  mov     rcx, rdi; void *
0x18001fc21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fc26  mov     qword ptr [rbx+48h], 0
0x18001fc2e  mov     rbx, [rsp+28h+arg_0]
0x18001fc33  mov     rbp, [rsp+28h+arg_8]
0x18001fc38  add     rsp, 20h
0x18001fc3c  pop     rdi
0x18001fc3d  retn
```
