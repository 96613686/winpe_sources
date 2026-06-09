# CAVICmpStream::CS::ReadFormat(long,void *,long *)

- ea: `0x18000de80`
- end: `0x18000df86`
- name: `?ReadFormat@CS@CAVICmpStream@@UEAAJJPEAXPEAJ@Z`
- size: `262`
- prototype: `int(CAVICmpStream::CS *__hidden this, int, void *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000de80`
- `0x18000e664`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::CS::ReadFormat(CAVICmpStream::CS *this, unsigned int a2, char *a3, int *a4)
{
  __int64 v4; // rbx
  __int64 result; // rax
  __int64 v9; // rcx
  unsigned int *v10; // rax
  char *v11; // rdi
  int v12; // eax
  int v13; // ecx
  char *v14; // rdx
  size_t v15; // r8
  char *v16; // rcx
  int v17; // eax
  int *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rax

  v4 = *((_QWORD *)this + 1);
  if ( *(_QWORD *)(v4 + 264)
    || (result = CAVICmpStream::SetUpCompression(*((CAVICmpStream **)this + 1)), !(_DWORD)result) )
  {
    v9 = *(_QWORD *)(v4 + 264);
    if ( v9 )
    {
      v10 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, a2);
      v11 = (char *)v10;
      if ( v10 )
      {
        if ( *(_QWORD *)(v4 + 280) )
        {
          if ( !a3 )
            goto LABEL_20;
          v17 = *a4;
          if ( *a4 >= *(_DWORD *)(v4 + 328) )
            v17 = *(_DWORD *)(v4 + 328);
          memmove_0(a3, *(const void **)(v4 + 320), v17);
          v18 = *(int **)(v4 + 320);
          if ( !v18[8] || *v18 < 0 || *v18 >= *a4 )
            goto LABEL_20;
          v15 = (unsigned int)(*a4 - *v18);
          v19 = (unsigned int)v18[8];
          v20 = (unsigned int)*v18;
          v21 = 4 * v19;
          if ( v15 >= v21 )
            v15 = v21;
          v14 = &v11[*(unsigned int *)v11];
          v16 = &a3[v20];
        }
        else
        {
          v12 = *v10 + 4 * v10[8];
          *(_DWORD *)(v4 + 328) = v12;
          if ( !a3 )
          {
LABEL_20:
            *a4 = *(_DWORD *)(v4 + 328);
            return 0;
          }
          v13 = *a4;
          v14 = v11;
          if ( *a4 >= v12 )
            v13 = v12;
          v15 = v13;
          v16 = a3;
        }
        memmove_0(v16, v14, v15);
        goto LABEL_20;
      }
    }
    return 2147762279LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000de80  push    rbx
0x18000de82  push    rsi
0x18000de83  push    rdi
0x18000de84  push    r14
0x18000de86  sub     rsp, 28h
0x18000de8a  mov     rbx, [rcx+8]
0x18000de8e  mov     r14, r9
0x18000de91  mov     rsi, r8
0x18000de94  mov     edi, edx
0x18000de96  cmp     qword ptr [rbx+108h], 0
0x18000de9e  jnz     short loc_18000DEB0
0x18000dea0  mov     rcx, rbx; this
0x18000dea3  call    ?SetUpCompression@CAVICmpStream@@QEAAJXZ; CAVICmpStream::SetUpCompression(void)
0x18000dea8  test    eax, eax
0x18000deaa  jnz     loc_18000DF7C
0x18000deb0  mov     rcx, [rbx+108h]
0x18000deb7  test    rcx, rcx
0x18000deba  jz      loc_18000DF77
0x18000dec0  mov     rax, [rcx]
0x18000dec3  mov     edx, edi
0x18000dec5  mov     rax, [rax+18h]
0x18000dec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dece  mov     rdi, rax
0x18000ded1  test    rax, rax
0x18000ded4  jz      loc_18000DF77
0x18000deda  cmp     qword ptr [rbx+118h], 0
0x18000dee2  jnz     short loc_18000DF0A
0x18000dee4  mov     edx, [rax+20h]
0x18000dee7  mov     ecx, [rax]
0x18000dee9  lea     eax, [rcx+rdx*4]
0x18000deec  mov     [rbx+148h], eax
0x18000def2  test    rsi, rsi
0x18000def5  jz      short loc_18000DF6A
0x18000def7  mov     ecx, [r14]
0x18000defa  mov     rdx, rdi
0x18000defd  cmp     ecx, eax
0x18000deff  cmovge  ecx, eax
0x18000df02  movsxd  r8, ecx
0x18000df05  mov     rcx, rsi
0x18000df08  jmp     short loc_18000DF65
0x18000df0a  test    rsi, rsi
0x18000df0d  jz      short loc_18000DF6A
0x18000df0f  mov     ecx, [rbx+148h]
0x18000df15  mov     eax, [r14]
0x18000df18  cmp     eax, ecx
0x18000df1a  mov     rdx, [rbx+140h]; Src
0x18000df21  cmovge  eax, ecx
0x18000df24  mov     rcx, rsi; void *
0x18000df27  movsxd  r8, eax; Size
0x18000df2a  call    memmove_0
0x18000df2f  mov     rcx, [rbx+140h]
0x18000df36  cmp     dword ptr [rcx+20h], 0
0x18000df3a  jbe     short loc_18000DF6A
0x18000df3c  cmp     dword ptr [rcx], 0
0x18000df3f  jl      short loc_18000DF6A
0x18000df41  mov     eax, [r14]
0x18000df44  cmp     [rcx], eax
0x18000df46  jge     short loc_18000DF6A
0x18000df48  sub     eax, [rcx]
0x18000df4a  mov     edx, [rdi]
0x18000df4c  mov     r8d, eax
0x18000df4f  mov     eax, [rcx+20h]
0x18000df52  mov     ecx, [rcx]
0x18000df54  shl     rax, 2
0x18000df58  cmp     r8, rax
0x18000df5b  cmovnb  r8, rax; Size
0x18000df5f  add     rdx, rdi; Src
0x18000df62  add     rcx, rsi; void *
0x18000df65  call    memmove_0
0x18000df6a  mov     eax, [rbx+148h]
0x18000df70  mov     [r14], eax
0x18000df73  xor     eax, eax
0x18000df75  jmp     short loc_18000DF7C
0x18000df77  mov     eax, 80044067h
0x18000df7c  add     rsp, 28h
0x18000df80  pop     r14
0x18000df82  pop     rdi
0x18000df83  pop     rsi
0x18000df84  pop     rbx
0x18000df85  retn
```
