# CAVICmpStream::CS::Read(long,long,void *,long,long *,long *)

- ea: `0x18000dc50`
- end: `0x18000de06`
- name: `?Read@CS@CAVICmpStream@@UEAAJJJPEAXJPEAJ1@Z`
- size: `438`
- prototype: `int(CAVICmpStream::CS *__hidden this, int, int, void *, int, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d7f0`

## callees

- `0x18000d86c`
- `0x18000dc50`
- `0x18000e664`
- `0x180017365`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CAVICmpStream::CS::Read(
        CAVICmpStream::CS *this,
        int a2,
        __int64 a3,
        void *a4,
        unsigned int Size,
        int *a6,
        int *a7)
{
  __int64 v7; // rbx
  __int64 result; // rax
  __int64 v11; // rcx
  int *v12; // r9
  unsigned int v13; // eax
  size_t v14; // r8
  char *v15; // rdx
  int v16; // eax
  bool v17; // cc
  __int64 v18; // rcx
  struct tagBITMAPINFOHEADER *v19; // rax
  unsigned int v20; // ecx

  v7 = *((_QWORD *)this + 1);
  if ( !*(_QWORD *)(v7 + 264) )
  {
    result = CAVICmpStream::SetUpCompression(*((CAVICmpStream **)this + 1));
    if ( (_DWORD)result )
      return result;
  }
  if ( *(_QWORD *)(v7 + 280) )
  {
    v16 = *(_DWORD *)(v7 + 272);
    v17 = v16 < a2;
    if ( v16 <= a2 )
      goto LABEL_21;
    *(_DWORD *)(v7 + 272) = -1;
    v16 = -1;
    *(_QWORD *)(v7 + 376) = 10000;
    *(_DWORD *)(v7 + 384) = 0;
    while ( 1 )
    {
      v17 = v16 < a2;
LABEL_21:
      if ( !v17 )
        break;
      v18 = *(_QWORD *)(v7 + 264);
      *(_DWORD *)(v7 + 272) = v16 + 1;
      if ( !v18
        || (v19 = (struct tagBITMAPINFOHEADER *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18)) == 0
        || (unsigned int)CAVICmpStream::ICCrunch(
                           (CAVICmpStream *)v7,
                           v19,
                           (char *)&v19->biSize + 4 * (int)v19->biClrUsed + (int)v19->biSize) )
      {
        *(_DWORD *)(v7 + 272) = -1;
        result = 2147762280LL;
        *(_QWORD *)(v7 + 376) = 10000;
        *(_DWORD *)(v7 + 384) = 0;
        return result;
      }
      v16 = *(_DWORD *)(v7 + 272);
    }
    if ( a6 )
      *a6 = *(_DWORD *)(*(_QWORD *)(v7 + 288) + 20LL);
    if ( !a4 )
      goto LABEL_32;
    v20 = *(_DWORD *)(*(_QWORD *)(v7 + 288) + 20LL);
    if ( (int)v20 > (int)Size )
      return 2147762292LL;
    v15 = *(char **)(v7 + 296);
    if ( v20 > Size )
      v20 = Size;
    v14 = v20;
  }
  else
  {
    v11 = *(_QWORD *)(v7 + 264);
    if ( !v11 )
      return 2147762279LL;
    v12 = (int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, (unsigned int)a2);
    if ( !v12 )
      return 2147762279LL;
    if ( a6 )
      *a6 = v12[5];
    if ( !a4 )
      goto LABEL_32;
    v13 = v12[5];
    if ( (int)v13 > (int)Size )
      return 2147762292LL;
    if ( v13 > Size )
      v13 = Size;
    v14 = v13;
    v15 = (char *)&v12[v12[8]] + *v12;
  }
  memmove_0(a4, v15, v14);
LABEL_32:
  if ( a7 )
    *a7 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000dc50  mov     [rsp+arg_0], rbx
0x18000dc55  mov     [rsp+arg_8], rsi
0x18000dc5a  push    rdi
0x18000dc5b  sub     rsp, 20h
0x18000dc5f  mov     rbx, [rcx+8]
0x18000dc63  mov     rsi, r9
0x18000dc66  mov     edi, edx
0x18000dc68  cmp     qword ptr [rbx+108h], 0
0x18000dc70  jnz     short loc_18000DC82
0x18000dc72  mov     rcx, rbx; this
0x18000dc75  call    ?SetUpCompression@CAVICmpStream@@QEAAJXZ; CAVICmpStream::SetUpCompression(void)
0x18000dc7a  test    eax, eax
0x18000dc7c  jnz     loc_18000DDF6
0x18000dc82  cmp     qword ptr [rbx+118h], 0
0x18000dc8a  jnz     short loc_18000DCFA
0x18000dc8c  mov     rcx, [rbx+108h]
0x18000dc93  test    rcx, rcx
0x18000dc96  jz      short loc_18000DCF0
0x18000dc98  mov     rax, [rcx]
0x18000dc9b  mov     edx, edi
0x18000dc9d  mov     rax, [rax+18h]
0x18000dca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dca6  mov     r9, rax
0x18000dca9  test    rax, rax
0x18000dcac  jz      short loc_18000DCF0
0x18000dcae  mov     rax, [rsp+28h+arg_28]
0x18000dcb3  test    rax, rax
0x18000dcb6  jz      short loc_18000DCBE
0x18000dcb8  mov     ecx, [r9+14h]
0x18000dcbc  mov     [rax], ecx
0x18000dcbe  test    rsi, rsi
0x18000dcc1  jz      loc_18000DDE4
0x18000dcc7  mov     eax, [r9+14h]
0x18000dccb  mov     ecx, dword ptr [rsp+28h+Size]
0x18000dccf  cmp     eax, ecx
0x18000dcd1  jg      loc_18000DDA2
0x18000dcd7  movsxd  rdx, dword ptr [r9+20h]
0x18000dcdb  cmova   eax, ecx
0x18000dcde  movsxd  rcx, dword ptr [r9]
0x18000dce1  add     rcx, r9
0x18000dce4  mov     r8d, eax
0x18000dce7  lea     rdx, [rcx+rdx*4]
0x18000dceb  jmp     loc_18000DDDC
0x18000dcf0  mov     eax, 80044067h
0x18000dcf5  jmp     loc_18000DDF6
0x18000dcfa  mov     eax, [rbx+110h]
0x18000dd00  cmp     eax, edi
0x18000dd02  jle     short loc_18000DD73
0x18000dd04  mov     dword ptr [rbx+110h], 0FFFFFFFFh
0x18000dd0e  or      eax, 0FFFFFFFFh
0x18000dd11  mov     qword ptr [rbx+178h], 2710h
0x18000dd1c  mov     dword ptr [rbx+180h], 0
0x18000dd26  jmp     short loc_18000DD71
0x18000dd28  mov     rcx, [rbx+108h]
0x18000dd2f  lea     edx, [rax+1]
0x18000dd32  mov     [rbx+110h], edx
0x18000dd38  test    rcx, rcx
0x18000dd3b  jz      short loc_18000DDA9
0x18000dd3d  mov     rax, [rcx]
0x18000dd40  mov     rax, [rax+18h]
0x18000dd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd49  test    rax, rax
0x18000dd4c  jz      short loc_18000DDA9
0x18000dd4e  movsxd  rdx, dword ptr [rax]
0x18000dd51  mov     rcx, rbx; this
0x18000dd54  movsxd  r8, dword ptr [rax+20h]
0x18000dd58  add     rdx, rax
0x18000dd5b  lea     r8, [rdx+r8*4]; void *
0x18000dd5f  mov     rdx, rax; struct tagBITMAPINFOHEADER *
0x18000dd62  call    ?ICCrunch@CAVICmpStream@@QEAAJPEAUtagBITMAPINFOHEADER@@PEAX@Z; CAVICmpStream::ICCrunch(tagBITMAPINFOHEADER *,void *)
0x18000dd67  test    eax, eax
0x18000dd69  jnz     short loc_18000DDA9
0x18000dd6b  mov     eax, [rbx+110h]
0x18000dd71  cmp     eax, edi
0x18000dd73  jl      short loc_18000DD28
0x18000dd75  mov     rdx, [rsp+28h+arg_28]
0x18000dd7a  test    rdx, rdx
0x18000dd7d  jz      short loc_18000DD8B
0x18000dd7f  mov     rax, [rbx+120h]
0x18000dd86  mov     ecx, [rax+14h]
0x18000dd89  mov     [rdx], ecx
0x18000dd8b  test    rsi, rsi
0x18000dd8e  jz      short loc_18000DDE4
0x18000dd90  mov     rax, [rbx+120h]
0x18000dd97  mov     ecx, [rax+14h]
0x18000dd9a  mov     eax, dword ptr [rsp+28h+Size]
0x18000dd9e  cmp     ecx, eax
0x18000dda0  jle     short loc_18000DDCF
0x18000dda2  mov     eax, 80044074h
0x18000dda7  jmp     short loc_18000DDF6
0x18000dda9  mov     dword ptr [rbx+110h], 0FFFFFFFFh
0x18000ddb3  mov     eax, 80044068h
0x18000ddb8  mov     qword ptr [rbx+178h], 2710h
0x18000ddc3  mov     dword ptr [rbx+180h], 0
0x18000ddcd  jmp     short loc_18000DDF6
0x18000ddcf  mov     rdx, [rbx+128h]; Src
0x18000ddd6  cmova   ecx, eax
0x18000ddd9  mov     r8d, ecx; Size
0x18000dddc  mov     rcx, rsi; void *
0x18000dddf  call    memmove_0
0x18000dde4  mov     rax, [rsp+28h+arg_30]
0x18000dde9  test    rax, rax
0x18000ddec  jz      short loc_18000DDF4
0x18000ddee  mov     dword ptr [rax], 1
0x18000ddf4  xor     eax, eax
0x18000ddf6  mov     rbx, [rsp+28h+arg_0]
0x18000ddfb  mov     rsi, [rsp+28h+arg_8]
0x18000de00  add     rsp, 20h
0x18000de04  pop     rdi
0x18000de05  retn
```
