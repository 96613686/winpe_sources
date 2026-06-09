# CVideoObjectDecoder::RenderFrame_Planar(uchar *,uchar *,uchar *)

- ea: `0x18000bde4`
- end: `0x18000c09d`
- name: `?RenderFrame_Planar@CVideoObjectDecoder@@AEAAXPEAE00@Z`
- size: `697`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f440`
- `0x18000f9d0`
- `0x180010600`
- `0x180010f80`

## callees

- `0x18000bde4`
- `0x180022010`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::RenderFrame_Planar(
        CVideoObjectDecoder *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 v4; // rax
  unsigned int v6; // r15d
  unsigned __int8 *v7; // rdi
  __int64 v8; // rsi
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rdx
  __int64 v11; // rbp
  _DWORD *v12; // r8
  __int64 v13; // r14
  unsigned int v14; // eax
  unsigned __int8 *v15; // r13
  unsigned int v16; // ecx
  unsigned __int8 *v17; // r12
  __int64 v18; // rsi
  __int64 v19; // rdi
  unsigned __int8 *v20; // rbp
  __int64 v21; // r14
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int8 *v27; // [rsp+70h] [rbp-78h]
  __int64 v28; // [rsp+78h] [rbp-70h]
  __int64 v29; // [rsp+80h] [rbp-68h]
  __int64 v30; // [rsp+88h] [rbp-60h]
  __int64 v31; // [rsp+98h] [rbp-50h]
  unsigned int v32; // [rsp+F0h] [rbp+8h]
  _DWORD *v33; // [rsp+F8h] [rbp+10h]
  unsigned __int8 *v34; // [rsp+100h] [rbp+18h]
  unsigned __int8 *v35; // [rsp+108h] [rbp+20h]

  v4 = *((int *)this + 89);
  v6 = 0;
  v7 = &a2[*((int *)this + 88)];
  v34 = v7;
  v8 = *((_QWORD *)this + 469);
  v9 = &a3[v4];
  v10 = &a4[v4];
  v11 = v8 + *((int *)this + 360);
  v12 = (_DWORD *)*((_QWORD *)this + 24);
  v13 = v8 + *((int *)this + 356);
  v35 = v9;
  v27 = &a4[v4];
  v28 = v8;
  v29 = v11;
  v30 = v13;
  v33 = v12;
  if ( !*((_DWORD *)this + 29) )
    return;
  do
  {
    v14 = *((_DWORD *)this + 28);
    if ( !v14 )
      goto LABEL_19;
    v31 = v8;
    v15 = v9;
    v16 = 0;
    v17 = v7;
    v18 = v11;
    v32 = 0;
    v19 = v13;
    v20 = v10;
    v21 = v31;
    do
    {
      if ( !*v12 || *((_DWORD *)this + 341) )
      {
        if ( *((_DWORD *)this + 72) )
        {
LABEL_7:
          (*((void (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, _DWORD, _DWORD, _DWORD, _DWORD))this
           + 191))(
            v21,
            v18,
            v19,
            v17,
            v15,
            v20,
            *((_DWORD *)this + 84),
            *((_DWORD *)this + 85),
            *((_DWORD *)this + 342),
            *((_DWORD *)this + 364));
LABEL_16:
          v16 = v32;
          goto LABEL_17;
        }
        if ( v16 == v14 - 1 )
        {
          v22 = *((_DWORD *)this + 66) - *((_DWORD *)this + 73) + 16;
        }
        else
        {
          if ( v6 != *((_DWORD *)this + 29) - 1 )
            goto LABEL_7;
          v22 = 16;
        }
        if ( v6 == *((_DWORD *)this + 29) - 1 )
          v23 = *((_DWORD *)this + 67) - *((_DWORD *)this + 75) + 16;
        else
          v23 = 16;
        (*((void (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, _DWORD, _DWORD, _DWORD, _DWORD, int, int))this
         + 192))(
          v21,
          v18,
          v19,
          v17,
          v15,
          v20,
          *((_DWORD *)this + 84),
          *((_DWORD *)this + 85),
          *((_DWORD *)this + 342),
          *((_DWORD *)this + 364),
          v22,
          v23);
        goto LABEL_16;
      }
LABEL_17:
      ++v16;
      v33 += 18;
      v21 += *((int *)this + 345);
      v24 = *((int *)this + 366);
      v17 += 16;
      v12 = v33;
      v18 += v24;
      v19 += v24;
      v32 = v16;
      v14 = *((_DWORD *)this + 28);
      v15 += 8;
      v20 += 8;
    }
    while ( v16 < v14 );
    v7 = v34;
    v8 = v28;
    v11 = v29;
    v13 = v30;
    v9 = v35;
    v10 = v27;
LABEL_19:
    ++v6;
    v7 += *((int *)this + 922);
    v25 = *((int *)this + 923);
    v9 += v25;
    v34 = v7;
    v10 += v25;
    v35 = v9;
    v8 += *((int *)this + 347);
    v27 = v10;
    v26 = *((int *)this + 367);
    v11 += v26;
    v28 = v8;
    v13 += v26;
    v29 = v11;
    v30 = v13;
  }
  while ( v6 < *((_DWORD *)this + 29) );
}

```

## disassembly

```asm
0x18000bde4  push    rbx
0x18000bde6  push    rbp
0x18000bde7  push    rsi
0x18000bde8  push    rdi
0x18000bde9  push    r12
0x18000bdeb  push    r13
0x18000bded  push    r14
0x18000bdef  push    r15
0x18000bdf1  sub     rsp, 0A8h
0x18000bdf8  movsxd  rax, dword ptr [rcx+164h]
0x18000bdff  mov     rbx, rcx
0x18000be02  movsxd  rdi, dword ptr [rcx+160h]
0x18000be09  xor     r15d, r15d
0x18000be0c  add     rdi, rdx
0x18000be0f  mov     [rsp+0E8h+arg_10], rdi
0x18000be17  mov     rsi, [rbx+0EA8h]
0x18000be1e  lea     rcx, [rax+r8]
0x18000be22  movsxd  rbp, dword ptr [rbx+5A0h]
0x18000be29  lea     rdx, [rax+r9]
0x18000be2d  movsxd  r14, dword ptr [rbx+590h]
0x18000be34  add     rbp, rsi
0x18000be37  mov     r8, [rbx+0C0h]
0x18000be3e  add     r14, rsi
0x18000be41  mov     [rsp+0E8h+arg_18], rcx
0x18000be49  mov     [rsp+0E8h+var_78], rdx
0x18000be4e  mov     [rsp+0E8h+var_70], rsi
0x18000be53  mov     [rsp+0E8h+var_68], rbp
0x18000be5b  mov     [rsp+0E8h+var_60], r14
0x18000be63  mov     [rsp+0E8h+arg_8], r8
0x18000be6b  cmp     [rbx+74h], r15d
0x18000be6f  jbe     loc_18000C089
0x18000be75  mov     eax, [rbx+70h]
0x18000be78  test    eax, eax
0x18000be7a  jz      loc_18000C024
0x18000be80  mov     [rsp+0E8h+var_50], rsi
0x18000be88  mov     r13, rcx
0x18000be8b  xor     ecx, ecx
0x18000be8d  mov     r12, rdi
0x18000be90  mov     rsi, rbp
0x18000be93  mov     [rsp+0E8h+arg_0], ecx
0x18000be9a  mov     rdi, r14
0x18000be9d  mov     rbp, rdx
0x18000bea0  mov     r14, [rsp+0E8h+var_50]
0x18000bea8  cmp     dword ptr [r8], 0
0x18000beac  jz      short loc_18000BEBB
0x18000beae  cmp     dword ptr [rbx+554h], 0
0x18000beb5  jz      loc_18000BFB2
0x18000bebb  cmp     dword ptr [rbx+120h], 0
0x18000bec2  jz      short loc_18000BF13
0x18000bec4  mov     ecx, [rbx+5B0h]
0x18000beca  mov     r9, r12
0x18000becd  mov     rax, [rbx+5F8h]
0x18000bed4  mov     r8, rdi
0x18000bed7  mov     [rsp+0E8h+var_A0], ecx
0x18000bedb  mov     rdx, rsi
0x18000bede  mov     ecx, [rbx+558h]
0x18000bee4  mov     [rsp+0E8h+var_A8], ecx
0x18000bee8  mov     ecx, [rbx+154h]
0x18000beee  mov     [rsp+0E8h+var_B0], ecx
0x18000bef2  mov     ecx, [rbx+150h]
0x18000bef8  mov     [rsp+0E8h+var_B8], ecx
0x18000befc  mov     rcx, r14
0x18000beff  mov     [rsp+0E8h+var_C0], rbp
0x18000bf04  mov     [rsp+0E8h+var_C8], r13
0x18000bf09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf0e  jmp     loc_18000BFAB
0x18000bf13  dec     eax
0x18000bf15  cmp     ecx, eax
0x18000bf17  jz      short loc_18000BF2A
0x18000bf19  mov     eax, [rbx+74h]
0x18000bf1c  dec     eax
0x18000bf1e  cmp     r15d, eax
0x18000bf21  jnz     short loc_18000BEC4
0x18000bf23  mov     ecx, 10h
0x18000bf28  jmp     short loc_18000BF39
0x18000bf2a  mov     ecx, [rbx+108h]
0x18000bf30  sub     ecx, [rbx+124h]
0x18000bf36  add     ecx, 10h
0x18000bf39  mov     eax, [rbx+74h]
0x18000bf3c  dec     eax
0x18000bf3e  cmp     r15d, eax
0x18000bf41  jz      short loc_18000BF4A
0x18000bf43  mov     eax, 10h
0x18000bf48  jmp     short loc_18000BF59
0x18000bf4a  mov     eax, [rbx+10Ch]
0x18000bf50  sub     eax, [rbx+12Ch]
0x18000bf56  add     eax, 10h
0x18000bf59  mov     [rsp+0E8h+var_90], eax
0x18000bf5d  mov     r9, r12
0x18000bf60  mov     rax, [rbx+600h]
0x18000bf67  mov     r8, rdi
0x18000bf6a  mov     [rsp+0E8h+var_98], ecx
0x18000bf6e  mov     rdx, rsi
0x18000bf71  mov     ecx, [rbx+5B0h]
0x18000bf77  mov     [rsp+0E8h+var_A0], ecx
0x18000bf7b  mov     ecx, [rbx+558h]
0x18000bf81  mov     [rsp+0E8h+var_A8], ecx
0x18000bf85  mov     ecx, [rbx+154h]
0x18000bf8b  mov     [rsp+0E8h+var_B0], ecx
0x18000bf8f  mov     ecx, [rbx+150h]
0x18000bf95  mov     [rsp+0E8h+var_B8], ecx
0x18000bf99  mov     rcx, r14
0x18000bf9c  mov     [rsp+0E8h+var_C0], rbp
0x18000bfa1  mov     [rsp+0E8h+var_C8], r13
0x18000bfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfab  mov     ecx, [rsp+0E8h+arg_0]
0x18000bfb2  movsxd  rax, dword ptr [rbx+564h]
0x18000bfb9  inc     ecx
0x18000bfbb  add     [rsp+0E8h+arg_8], 48h ; 'H'
0x18000bfc4  add     r14, rax
0x18000bfc7  movsxd  rax, dword ptr [rbx+5B8h]
0x18000bfce  add     r12, 10h
0x18000bfd2  mov     r8, [rsp+0E8h+arg_8]
0x18000bfda  add     rsi, rax
0x18000bfdd  add     rdi, rax
0x18000bfe0  mov     [rsp+0E8h+arg_0], ecx
0x18000bfe7  mov     eax, [rbx+70h]
0x18000bfea  add     r13, 8
0x18000bfee  add     rbp, 8
0x18000bff2  cmp     ecx, eax
0x18000bff4  jb      loc_18000BEA8
0x18000bffa  mov     rdi, [rsp+0E8h+arg_10]
0x18000c002  mov     rsi, [rsp+0E8h+var_70]
0x18000c007  mov     rbp, [rsp+0E8h+var_68]
0x18000c00f  mov     r14, [rsp+0E8h+var_60]
0x18000c017  mov     rcx, [rsp+0E8h+arg_18]
0x18000c01f  mov     rdx, [rsp+0E8h+var_78]
0x18000c024  movsxd  rax, dword ptr [rbx+0E68h]
0x18000c02b  inc     r15d
0x18000c02e  add     rdi, rax
0x18000c031  movsxd  rax, dword ptr [rbx+0E6Ch]
0x18000c038  add     rcx, rax
0x18000c03b  mov     [rsp+0E8h+arg_10], rdi
0x18000c043  add     rdx, rax
0x18000c046  mov     [rsp+0E8h+arg_18], rcx
0x18000c04e  movsxd  rax, dword ptr [rbx+56Ch]
0x18000c055  add     rsi, rax
0x18000c058  mov     [rsp+0E8h+var_78], rdx
0x18000c05d  movsxd  rax, dword ptr [rbx+5BCh]
0x18000c064  add     rbp, rax
0x18000c067  mov     [rsp+0E8h+var_70], rsi
0x18000c06c  add     r14, rax
0x18000c06f  mov     [rsp+0E8h+var_68], rbp
0x18000c077  mov     [rsp+0E8h+var_60], r14
0x18000c07f  cmp     r15d, [rbx+74h]
0x18000c083  jb      loc_18000BE75
0x18000c089  add     rsp, 0A8h
0x18000c090  pop     r15
0x18000c092  pop     r14
0x18000c094  pop     r13
0x18000c096  pop     r12
0x18000c098  pop     rdi
0x18000c099  pop     rsi
0x18000c09a  pop     rbp
0x18000c09b  pop     rbx
0x18000c09c  retn
```
