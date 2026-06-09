# CPictureCYUV420::Clean(void)

- ea: `0x18001fc6c`
- end: `0x18001fcfe`
- name: `?Clean@CPictureCYUV420@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(CPictureCYUV420 *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009b88`
- `0x180012d34`
- `0x18001faf0`

## callees

- `0x180001450`
- `0x18001fc6c`
- `0x18001fdc8`

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
0x18001fc6c  mov     [rsp+arg_0], rbx
0x18001fc71  mov     [rsp+arg_8], rbp
0x18001fc76  push    rdi
0x18001fc77  sub     rsp, 20h
0x18001fc7b  mov     rdi, [rcx+38h]
0x18001fc7f  mov     rbx, rcx
0x18001fc82  mov     ebp, 20h ; ' '
0x18001fc87  test    rdi, rdi
0x18001fc8a  jz      short loc_18001FCA6
0x18001fc8c  mov     rcx, rdi; this
0x18001fc8f  call    ??1CU8Image@@QEAA@XZ; CU8Image::~CU8Image(void)
0x18001fc94  mov     edx, ebp; unsigned __int64
0x18001fc96  mov     rcx, rdi; void *
0x18001fc99  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fc9e  mov     qword ptr [rbx+38h], 0
0x18001fca6  mov     rdi, [rbx+40h]
0x18001fcaa  test    rdi, rdi
0x18001fcad  jz      short loc_18001FCCA
0x18001fcaf  mov     rcx, rdi; this
0x18001fcb2  call    ??1CU8Image@@QEAA@XZ; CU8Image::~CU8Image(void)
0x18001fcb7  mov     rdx, rbp; unsigned __int64
0x18001fcba  mov     rcx, rdi; void *
0x18001fcbd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fcc2  mov     qword ptr [rbx+40h], 0
0x18001fcca  mov     rdi, [rbx+48h]
0x18001fcce  test    rdi, rdi
0x18001fcd1  jz      short loc_18001FCEE
0x18001fcd3  mov     rcx, rdi; this
0x18001fcd6  call    ??1CU8Image@@QEAA@XZ; CU8Image::~CU8Image(void)
0x18001fcdb  mov     rdx, rbp; unsigned __int64
0x18001fcde  mov     rcx, rdi; void *
0x18001fce1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fce6  mov     qword ptr [rbx+48h], 0
0x18001fcee  mov     rbx, [rsp+28h+arg_0]
0x18001fcf3  mov     rbp, [rsp+28h+arg_8]
0x18001fcf8  add     rsp, 20h
0x18001fcfc  pop     rdi
0x18001fcfd  retn
```
