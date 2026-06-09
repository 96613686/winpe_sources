# MemoryWriterImpl::WriteAlignedCount(void const *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18004de6c`
- end: `0x18004df4e`
- name: `?WriteAlignedCount@MemoryWriterImpl@@IEAAIPEBX_K11@Z`
- size: `226`
- prototype: `unsigned int(MemoryWriterImpl *__hidden this, const void *, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `18`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013e90`
- `0x180015f64`
- `0x1800194a0`
- `0x18001b440`
- `0x1800429b0`
- `0x180042e00`
- `0x180042edc`
- `0x180042fb0`
- `0x1800433f0`
- `0x18004df60`
- `0x18007ca20`
- `0x180096854`
- `0x180098920`
- `0x180098eb0`
- `0x1800994f4`
- `0x18009977c`
- `0x18009cf94`
- `0x1800a9228`

## callees

- `0x18004d664`
- `0x18004de6c`
- `0x18009e420`
- `0x1800ab0aa`
- `0x1800ab168`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004df20`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004df20`

## pseudocode

```c
__int64 __fastcall MemoryWriterImpl::WriteAlignedCount(
        unsigned __int64 this,
        const char *a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  const char *v5; // r10
  MemoryWriterImpl *v6; // rsi
  unsigned __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rdi
  char *v11; // rcx
  unsigned __int64 v12; // rax

  v5 = a2;
  v6 = (MemoryWriterImpl *)this;
  if ( a3 > 0xFFFFFFFF || HIDWORD(a4) && (_DWORD)a3 )
    goto LABEL_18;
  this = a4 * (unsigned int)a3;
  if ( !is_mul_ok(a4, a3) )
    goto LABEL_18;
  v7 = *((unsigned int *)v6 + 4);
  a2 = (const char *)(v7 + a5 - 1);
  if ( (unsigned __int64)a2 < v7 || (unsigned __int64)a2 > 0xFFFFFFFF )
    goto LABEL_18;
  v8 = (unsigned int)a2 & -(int)a5;
  a2 = *(const char **)v6;
  if ( *(_QWORD *)v6 )
  {
    v9 = *((_DWORD *)v6 + 2);
    if ( v9 < (unsigned int)v8
      || (v10 = (unsigned int)this, v9 - (unsigned int)v8 < (unsigned __int64)(unsigned int)this) )
    {
      FailAssert(0x4Bu, a2);
      __debugbreak();
    }
    if ( v5 && (_DWORD)this )
    {
      v11 = (char *)&a2[(unsigned int)v8];
      if ( v11 )
      {
        memcpy_0(v11, v5, (unsigned int)v10);
      }
      else
      {
        *(_DWORD *)_o__errno(0, a2, a3) = 22;
        invalid_parameter_noinfo();
      }
    }
  }
  else
  {
    v10 = (unsigned int)this;
  }
  this = (unsigned int)v8;
  v12 = v8 + v10;
  if ( v8 + v10 < (unsigned __int64)(unsigned int)v8 || v12 > 0xFFFFFFFF )
LABEL_18:
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(this, a2, a3, a4);
  *((_DWORD *)v6 + 4) = v12;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004de6c  push    rbx
0x18004de6e  push    rbp
0x18004de6f  push    rsi
0x18004de70  push    rdi
0x18004de71  sub     rsp, 28h
0x18004de75  mov     ebp, 0FFFFFFFFh
0x18004de7a  mov     r10, rdx
0x18004de7d  mov     rsi, rcx
0x18004de80  cmp     r8, rbp
0x18004de83  ja      loc_18004DF33
0x18004de89  mov     rax, r9
0x18004de8c  shr     rax, 20h
0x18004de90  test    eax, eax
0x18004de92  jnz     loc_18004DF44
0x18004de98  mov     ecx, r8d
0x18004de9b  imul    rcx, r9
0x18004de9f  mov     rax, rcx
0x18004dea2  shr     rax, 20h
0x18004dea6  test    eax, eax
0x18004dea8  jnz     loc_18004DF33
0x18004deae  mov     eax, [rsi+10h]
0x18004deb1  mov     rbx, [rsp+48h+arg_20]
0x18004deb6  lea     rdx, [rbx-1]
0x18004deba  add     rdx, rax
0x18004debd  cmp     rdx, rax
0x18004dec0  jb      short loc_18004DF33
0x18004dec2  cmp     rdx, rbp
0x18004dec5  ja      short loc_18004DF33
0x18004dec7  neg     ebx
0x18004dec9  and     ebx, edx
0x18004decb  mov     rdx, [rsi]; char *
0x18004dece  test    rdx, rdx
0x18004ded1  jz      short loc_18004DF00
0x18004ded3  mov     eax, [rsi+8]
0x18004ded6  cmp     eax, ebx
0x18004ded8  jb      short loc_18004DF39
0x18004deda  mov     edi, ecx
0x18004dedc  sub     eax, ebx
0x18004dede  cmp     rax, rdi
0x18004dee1  jb      short loc_18004DF39
0x18004dee3  test    r10, r10
0x18004dee6  jz      short loc_18004DF02
0x18004dee8  test    ecx, ecx
0x18004deea  jz      short loc_18004DF02
0x18004deec  mov     ecx, ebx
0x18004deee  add     rcx, rdx; void *
0x18004def1  jz      short loc_18004DF20
0x18004def3  mov     r8d, edi; Size
0x18004def6  mov     rdx, r10; Src
0x18004def9  call    memcpy_0
0x18004defe  jmp     short loc_18004DF02
0x18004df00  mov     edi, ecx
0x18004df02  mov     ecx, ebx
0x18004df04  lea     rax, [rbx+rdi]
0x18004df08  cmp     rax, rcx
0x18004df0b  jb      short loc_18004DF33
0x18004df0d  cmp     rax, rbp
0x18004df10  ja      short loc_18004DF33
0x18004df12  mov     [rsi+10h], eax
0x18004df15  mov     eax, ebx
0x18004df17  add     rsp, 28h
0x18004df1b  pop     rdi
0x18004df1c  pop     rsi
0x18004df1d  pop     rbp
0x18004df1e  pop     rbx
0x18004df1f  retn
0x18004df20  call    cs:__imp__o__errno
0x18004df26  mov     dword ptr [rax], 16h
0x18004df2c  call    _invalid_parameter_noinfo
0x18004df31  jmp     short loc_18004DF02
0x18004df33  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18004df39  mov     ecx, 4Bh ; 'K'; unsigned int
0x18004df3e  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x18004df43  int     3; Trap to Debugger
0x18004df44  test    r8d, r8d
0x18004df47  jnz     short loc_18004DF33
0x18004df49  jmp     loc_18004DE98
```
