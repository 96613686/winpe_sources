# CEditStream::ReadFormat(long,void *,long *)

- ea: `0x180012c74`
- end: `0x180012d5c`
- name: `?ReadFormat@CEditStream@@UEAAJJPEAXPEAJ@Z`
- size: `232`
- prototype: `int(CEditStream *__hidden this, int, void *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012c60`

## callees

- `0x180011300`
- `0x180012c74`
- `0x180012e88`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CEditStream::ReadFormat(CEditStream *this, int a2, void *a3, int *a4)
{
  CEditStream *v4; // rsi
  int v6; // ecx
  __int64 result; // rax
  struct tagBITMAPINFOHEADER *v10; // rax
  struct tagBITMAPINFOHEADER *v11; // rdx
  int v12; // ebx
  int v13; // eax
  struct IAVIStream *v14; // [rsp+50h] [rbp+8h] BYREF
  int v15; // [rsp+58h] [rbp+10h] BYREF

  v4 = (CEditStream *)((char *)this - 272);
  v14 = 0;
  v15 = 0;
  v6 = *((_DWORD *)this - 58);
  if ( a2 < v6 || a2 >= v6 + *((_DWORD *)this - 57) )
    return 2147762282LL;
  result = CEditStream::ResolveEdits(v4, a2, &v14, &v15, 0, 0);
  if ( !(_DWORD)result )
  {
    if ( *((_DWORD *)this - 12) )
    {
      v10 = CEditStream::CallGetFrame(v4, v14, v15);
      v11 = v10;
      if ( v10 )
      {
        v12 = v10->biSize + 4 * v10->biClrUsed;
        if ( a3 )
        {
          v13 = *a4;
          if ( *a4 >= v12 )
            v13 = v12;
          memmove_0(a3, v11, v13);
        }
        *a4 = v12;
        return 0;
      }
      else
      {
        return 2147500037LL;
      }
    }
    else
    {
      return ((__int64 (__fastcall *)(struct IAVIStream *, _QWORD, void *, int *))v14->lpVtbl->ReadFormat)(
               v14,
               (unsigned int)v15,
               a3,
               a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012c74  mov     rax, rsp
0x180012c77  mov     [rax+18h], rbx
0x180012c7b  push    rbp
0x180012c7c  push    rsi
0x180012c7d  push    rdi
0x180012c7e  sub     rsp, 30h
0x180012c82  lea     rsi, [rcx-110h]
0x180012c89  mov     qword ptr [rax+8], 0
0x180012c91  mov     rbx, rcx
0x180012c94  mov     dword ptr [rax+10h], 0
0x180012c9b  mov     ecx, [rsi+28h]
0x180012c9e  mov     rdi, r9
0x180012ca1  mov     rbp, r8
0x180012ca4  cmp     edx, ecx
0x180012ca6  jl      loc_180012D4A
0x180012cac  mov     r10d, [rbx-0E4h]
0x180012cb3  add     r10d, ecx
0x180012cb6  cmp     edx, r10d
0x180012cb9  jge     loc_180012D4A
0x180012cbf  mov     dword ptr [rax-20h], 0
0x180012cc6  lea     r9, [rax+10h]; int *
0x180012cca  lea     r8, [rax+8]; struct IAVIStream **
0x180012cce  mov     qword ptr [rax-28h], 0
0x180012cd6  mov     rcx, rsi; this
0x180012cd9  call    ?ResolveEdits@CEditStream@@AEAAJJPEAPEAUIAVIStream@@PEAJ1H@Z; CEditStream::ResolveEdits(long,IAVIStream * *,long *,long *,int)
0x180012cde  test    eax, eax
0x180012ce0  jnz     short loc_180012D4F
0x180012ce2  cmp     [rbx-30h], eax
0x180012ce5  jz      short loc_180012D2D
0x180012ce7  mov     r8d, [rsp+48h+arg_8]; int
0x180012cec  mov     rcx, rsi; this
0x180012cef  mov     rdx, [rsp+48h+arg_0]; struct IAVIStream *
0x180012cf4  call    ?CallGetFrame@CEditStream@@AEAAPEAUtagBITMAPINFOHEADER@@PEAUIAVIStream@@J@Z; CEditStream::CallGetFrame(IAVIStream *,long)
0x180012cf9  mov     rdx, rax; Src
0x180012cfc  test    rax, rax
0x180012cff  jnz     short loc_180012D08
0x180012d01  mov     eax, 80004005h
0x180012d06  jmp     short loc_180012D4F
0x180012d08  mov     ecx, [rax+20h]
0x180012d0b  mov     eax, [rax]
0x180012d0d  lea     ebx, [rax+rcx*4]
0x180012d10  test    rbp, rbp
0x180012d13  jz      short loc_180012D27
0x180012d15  mov     eax, [rdi]
0x180012d17  mov     rcx, rbp; void *
0x180012d1a  cmp     eax, ebx
0x180012d1c  cmovge  eax, ebx
0x180012d1f  movsxd  r8, eax; Size
0x180012d22  call    memmove_0
0x180012d27  mov     [rdi], ebx
0x180012d29  xor     eax, eax
0x180012d2b  jmp     short loc_180012D4F
0x180012d2d  mov     rcx, [rsp+48h+arg_0]
0x180012d32  mov     r9, rdi
0x180012d35  mov     edx, [rsp+48h+arg_8]
0x180012d39  mov     r8, rbp
0x180012d3c  mov     rax, [rcx]
0x180012d3f  mov     rax, [rax+30h]
0x180012d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d48  jmp     short loc_180012D4F
0x180012d4a  mov     eax, 8004406Ah
0x180012d4f  mov     rbx, [rsp+48h+arg_10]
0x180012d54  add     rsp, 30h
0x180012d58  pop     rdi
0x180012d59  pop     rsi
0x180012d5a  pop     rbp
0x180012d5b  retn
```
