# OpenRPCServerDebugInfo(ulong,void * *)

- ea: `0x180009df8`
- end: `0x18000a3fd`
- name: `?OpenRPCServerDebugInfo@@YAJKPEAPEAX@Z`
- size: `1541`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180007600`
- `0x180007cf0`
- `0x180009844`
- `0x180009db0`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180009990`
- `0x1800099b8`
- `0x180009acc`
- `0x180009d20`
- `0x180009df8`
- `0x18000a8a8`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a037`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a23b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a377`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a3bf`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a037`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a23b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a377`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000a3bf`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000a1be`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000a1be`

## pseudocode

```c
__int64 __fastcall OpenRPCServerDebugInfo(unsigned int a1, void **a2)
{
  __int64 result; // rax
  int v3; // r12d
  struct _LIST_ENTRY **v4; // rdi
  int v5; // ecx
  bool v6; // zf
  int Blink_high; // r9d
  int v8; // r8d
  struct _LIST_ENTRY *Flink; // rdx
  int v10; // r13d
  unsigned int v11; // esi
  char v12; // cl
  unsigned int *v13; // r14
  int v14; // edx
  struct _LIST_ENTRY *k; // rcx
  struct _LIST_ENTRY *v16; // rax
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v18; // rcx
  unsigned int v19; // eax
  struct _LIST_ENTRY **v20; // rax
  unsigned int v21; // eax
  struct _LIST_ENTRY *j; // rsi
  int v23; // r15d
  SIZE_T v24; // r13
  struct _LIST_ENTRY *v25; // rax
  struct _LIST_ENTRY *v26; // rcx
  struct _LIST_ENTRY *i; // rdi
  struct _LIST_ENTRY **p_Blink; // rdi
  _DWORD *v29; // rax
  struct _LIST_ENTRY *v30; // rdi
  struct _LIST_ENTRY **v31; // r14
  struct _LIST_ENTRY *v32; // rcx
  struct _LIST_ENTRY *v33; // rdi
  struct _LIST_ENTRY **v34; // r14
  struct _LIST_ENTRY *v35; // rcx
  struct _LIST_ENTRY v36; // [rsp+30h] [rbp-A8h] BYREF
  int v37; // [rsp+40h] [rbp-98h]
  struct _LIST_ENTRY *v38; // [rsp+48h] [rbp-90h] BYREF
  struct _LIST_ENTRY **v39; // [rsp+50h] [rbp-88h]
  int v40; // [rsp+58h] [rbp-80h]
  struct _LIST_ENTRY *v41; // [rsp+60h] [rbp-78h]
  struct _LIST_ENTRY v42; // [rsp+68h] [rbp-70h] BYREF
  void *v43; // [rsp+78h] [rbp-60h] BYREF
  void *SectionHandle; // [rsp+80h] [rbp-58h] BYREF
  int v45; // [rsp+88h] [rbp-50h]
  unsigned int *v46; // [rsp+90h] [rbp-48h]
  int v47; // [rsp+98h] [rbp-40h]

  SectionHandle = 0;
  v43 = 0;
  v36 = 0;
  v42 = 0;
  result = InitializeDbgLib();
  if ( (_DWORD)result )
    return result;
  v3 = 10;
  v4 = 0;
  v39 = 0;
  v45 = dword_180013B9C;
  v42.Flink = &v42;
  v42.Blink = &v42;
  v36.Flink = &v36;
  v36.Blink = &v36;
LABEL_3:
  v5 = 0;
LABEL_4:
  v6 = v3 == 0;
  if ( v3 <= 0 )
  {
LABEL_62:
    if ( v6 )
    {
      v11 = 1764;
    }
    else
    {
      for ( i = v36.Flink; i != &v36; i = i->Flink )
      {
        CloseDbgSection(i[-3].Blink, i[-2].Flink);
        i[-3].Blink = 0;
        i[-2].Flink = 0;
        i[-2].Blink = 0;
      }
      p_Blink = &v36.Flink[-3].Blink;
      v29 = operator new(0x18u);
      if ( v29 )
      {
        v29[4] = 0;
        *(_QWORD *)v29 = p_Blink;
        *((_QWORD *)v29 + 1) = p_Blink;
        v36.Blink->Flink = 0;
        v36.Flink = &v36;
        v36.Blink = &v36;
        *a2 = v29;
        v11 = 0;
      }
      else
      {
        v11 = 14;
      }
    }
    goto LABEL_70;
  }
  Blink_high = 0;
  v38 = 0;
  v8 = 0;
  Flink = v36.Flink;
  v10 = 0;
  v40 = 0;
  while ( 1 )
  {
    v41 = Flink;
    if ( Flink == &v36 )
    {
      if ( !v5 )
      {
        if ( v36.Flink == &v36 )
        {
          v12 = 1;
        }
        else
        {
          v12 = 0;
          v4 = &v36.Blink[-3].Blink;
          v39 = &v36.Blink[-3].Blink;
        }
        v13 = (unsigned int *)&v38;
        if ( v12 )
          v13 = 0;
        v46 = v13;
        while ( 1 )
        {
          if ( !v8 && !Blink_high && v13 )
          {
            for ( j = v36.Flink; ; j = j->Flink )
            {
              v41 = j;
              if ( j == &v36 )
                break;
              v4 = &j[-3].Blink;
              v39 = &j[-3].Blink;
              if ( !j[-1].Blink )
              {
                v23 = WORD1(v4[1]->Flink);
                v24 = (unsigned int)(v45 * v23);
                v25 = (struct _LIST_ENTRY *)VirtualAlloc(0, v24, 0x1000u, 4u);
                v4[4] = v25;
                if ( !v25 )
                {
                  v11 = 14;
                  v47 = 14;
                  goto LABEL_70;
                }
                memcpy_0(v25, v4[1], v24);
                *((_DWORD *)v4 + 7) = SWORD2(v4[1]->Flink);
                *((_DWORD *)v4 + 6) = v23;
              }
              v37 = 0;
            }
            v5 = 1;
            goto LABEL_4;
          }
          v14 = 0;
          if ( v13 )
          {
            for ( k = v42.Flink; ; k = k->Flink )
            {
              if ( k == &v42 )
                goto LABEL_38;
              v4 = &k[-3].Blink;
              v39 = &k[-3].Blink;
              if ( *v13 == LODWORD(k[-2].Blink) && v13[1] == *((_DWORD *)v4 + 5) )
                break;
            }
            v16 = k->Flink;
            if ( k->Flink->Blink != k || (Blink = k->Blink, Blink->Flink != k) )
LABEL_59:
              __fastfail(3u);
            Blink->Flink = v16;
            v16->Blink = Blink;
            v18 = v4[4];
            if ( v18 )
            {
              VirtualFree(v18, 0, 0x8000u);
              v4[4] = 0;
            }
            v14 = 1;
          }
LABEL_38:
          if ( !v14 )
          {
            v19 = OpenDbgSection(&SectionHandle, &v43, a1, v13);
            v11 = v19;
            if ( v19 == 2 )
            {
              if ( !v13 )
                goto LABEL_70;
LABEL_15:
              --v3;
              goto LABEL_3;
            }
            if ( v19 )
              goto LABEL_70;
            v20 = (struct _LIST_ENTRY **)operator new(0x38u);
            v4 = v20;
            if ( !v20 )
            {
              v11 = 14;
              CloseDbgSection(SectionHandle, v43);
              goto LABEL_70;
            }
            v39 = v20;
            *v20 = (struct _LIST_ENTRY *)SectionHandle;
            if ( v13 )
            {
              *((_DWORD *)v20 + 4) = *v13;
              v21 = v13[1];
            }
            else
            {
              *((_DWORD *)v20 + 4) = 0;
              v21 = 0;
            }
            *((_DWORD *)v4 + 5) = v21;
            v4[1] = (struct _LIST_ENTRY *)v43;
            v4[4] = 0;
          }
          v38 = v4[1]->Blink;
          v13 = (unsigned int *)&v38;
          v46 = (unsigned int *)&v38;
          v37 = 0;
          v26 = v36.Blink;
          if ( v36.Blink->Flink != &v36 )
            goto LABEL_59;
          v4[5] = &v36;
          v4[6] = v26;
          v26->Flink = (struct _LIST_ENTRY *)(v4 + 5);
          v36.Blink = (struct _LIST_ENTRY *)(v4 + 5);
          Blink_high = HIDWORD(v38);
          v8 = (int)v38;
        }
      }
      v6 = v3 == 0;
      goto LABEL_62;
    }
    v4 = &Flink[-3].Blink;
    v39 = &Flink[-3].Blink;
    if ( v8 == LODWORD(Flink[-2].Blink) && Blink_high == *((_DWORD *)v4 + 5) )
    {
      v8 = (int)v4[1]->Blink;
      LODWORD(v38) = v8;
      Blink_high = HIDWORD(v4[1]->Blink);
      HIDWORD(v38) = Blink_high;
      v37 = 0;
    }
    else
    {
      v10 = 1;
      v40 = 1;
    }
    if ( v10 )
      break;
    Flink = Flink->Flink;
  }
  if ( Flink != v36.Flink )
  {
    InconsistencyDetected(&v36, &v42, Flink, (struct tagOpenedDbgSection *)&Flink[-3].Blink, 0);
    goto LABEL_15;
  }
  v11 = 2;
LABEL_70:
  v30 = v36.Flink;
  while ( v30 != &v36 )
  {
    v31 = &v30[-3].Blink;
    v30 = v30->Flink;
    v32 = v31[4];
    if ( v32 )
      VirtualFree(v32, 0, 0x8000u);
    if ( *v31 )
      CloseDbgSection(*v31, v31[1]);
    operator delete(v31);
  }
  v33 = v42.Flink;
  while ( v33 != &v42 )
  {
    v34 = &v33[-3].Blink;
    v33 = v33->Flink;
    v35 = v34[4];
    if ( v35 )
      VirtualFree(v35, 0, 0x8000u);
    if ( *v34 )
      CloseDbgSection(*v34, v34[1]);
    operator delete(v34);
  }
  return v11;
}

```

## disassembly

```asm
0x180009df8  mov     rax, rsp
0x180009dfb  mov     [rax+10h], rdx
0x180009dff  mov     [rax+8], ecx
0x180009e02  push    rbx
0x180009e03  push    rsi
0x180009e04  push    rdi
0x180009e05  push    r12
0x180009e07  push    r13
0x180009e09  push    r14
0x180009e0b  push    r15
0x180009e0d  sub     rsp, 0A0h
0x180009e14  xor     ebx, ebx
0x180009e16  mov     [rax-58h], rbx
0x180009e1a  mov     [rax-60h], rbx
0x180009e1e  xorps   xmm0, xmm0
0x180009e21  movups  xmmword ptr [rsp+0D8h+var_A8.Flink], xmm0
0x180009e26  xorps   xmm1, xmm1
0x180009e29  movups  xmmword ptr [rax-70h], xmm1
0x180009e2d  call    ?InitializeDbgLib@@YAJXZ; InitializeDbgLib(void)
0x180009e32  test    eax, eax
0x180009e34  jnz     loc_18000A3EA
0x180009e3a  lea     r12d, [rbx+0Ah]
0x180009e3e  mov     edi, ebx
0x180009e40  mov     [rsp+0D8h+var_88], rbx
0x180009e45  mov     r15d, ebx
0x180009e48  mov     eax, cs:dword_180013B9C
0x180009e4e  mov     [rsp+0D8h+var_50], eax
0x180009e55  lea     rax, [rsp+0D8h+var_70]
0x180009e5a  mov     [rsp+0D8h+var_70.Flink], rax
0x180009e5f  lea     rax, [rsp+0D8h+var_70]
0x180009e64  mov     [rsp+0D8h+var_70.Blink], rax
0x180009e69  lea     rax, [rsp+0D8h+var_A8]
0x180009e6e  mov     [rsp+0D8h+var_A8.Flink], rax
0x180009e73  lea     rax, [rsp+0D8h+var_A8]
0x180009e78  mov     [rsp+0D8h+var_A8.Blink], rax
0x180009e7d  mov     [rsp+0D8h+arg_10], r12d
0x180009e85  mov     ecx, ebx
0x180009e87  mov     [rsp+0D8h+arg_18], ebx
0x180009e8e  test    r12d, r12d
0x180009e91  jle     loc_18000A2C8
0x180009e97  mov     r9d, ebx
0x180009e9a  mov     [rsp+0D8h+var_90], 0
0x180009ea3  mov     r8d, ebx
0x180009ea6  mov     rdx, [rsp+0D8h+var_A8.Flink]
0x180009eab  mov     r13d, ebx
0x180009eae  mov     [rsp+0D8h+var_80], ebx
0x180009eb2  mov     [rsp+0D8h+var_78], rdx
0x180009eb7  lea     rax, [rsp+0D8h+var_A8]
0x180009ebc  cmp     rdx, rax
0x180009ebf  jz      loc_180009F82
0x180009ec5  lea     rdi, [rdx-28h]
0x180009ec9  mov     [rsp+0D8h+var_88], rdi
0x180009ece  cmp     r8d, [rdi+10h]
0x180009ed2  jnz     short loc_180009F37
0x180009ed4  cmp     r9d, [rdi+14h]
0x180009ed8  jnz     short loc_180009F37
0x180009eda  mov     rax, [rdi+8]
0x180009ede  mov     r8d, [rax+8]
0x180009ee2  mov     dword ptr [rsp+0D8h+var_90], r8d
0x180009ee7  mov     rax, [rdi+8]
0x180009eeb  mov     r9d, [rax+0Ch]
0x180009eef  mov     dword ptr [rsp+0D8h+var_90+4], r9d
0x180009ef4  mov     r15d, ebx
0x180009ef7  mov     [rsp+0D8h+var_98], ebx
0x180009efb  jmp     short loc_180009F42
0x180009efd  mov     r15d, 1
0x180009f03  mov     [rsp+0D8h+var_98], r15d
0x180009f08  mov     r13d, r15d
0x180009f0b  mov     [rsp+0D8h+var_80], r15d
0x180009f10  xor     ebx, ebx
0x180009f12  mov     r12d, [rsp+0D8h+arg_10]
0x180009f1a  mov     rdi, [rsp+0D8h+var_88]
0x180009f1f  mov     rdx, [rsp+0D8h+var_78]
0x180009f24  mov     ecx, [rsp+0D8h+arg_18]
0x180009f2b  mov     r9d, dword ptr [rsp+0D8h+var_90+4]
0x180009f30  mov     r8d, dword ptr [rsp+0D8h+var_90]
0x180009f35  jmp     short loc_180009F42
0x180009f37  mov     r13d, 1
0x180009f3d  mov     [rsp+0D8h+var_80], r13d
0x180009f42  test    r13d, r13d
0x180009f45  jz      short loc_180009F7A
0x180009f47  cmp     rdx, [rsp+0D8h+var_A8.Flink]
0x180009f4c  jnz     short loc_180009F58
0x180009f4e  mov     esi, 2
0x180009f53  jmp     loc_18000A358
0x180009f58  mov     [rsp+0D8h+var_B8], r15d; int
0x180009f5d  mov     r9, rdi; struct tagOpenedDbgSection *
0x180009f60  mov     r8, rdx; struct _LIST_ENTRY *
0x180009f63  lea     rdx, [rsp+0D8h+var_70]; struct _LIST_ENTRY *
0x180009f68  lea     rcx, [rsp+0D8h+var_A8]; struct _LIST_ENTRY *
0x180009f6d  call    ?InconsistencyDetected@@YAXPEAU_LIST_ENTRY@@00PEAUtagOpenedDbgSection@@H@Z; InconsistencyDetected(_LIST_ENTRY *,_LIST_ENTRY *,_LIST_ENTRY *,tagOpenedDbgSection *,int)
0x180009f72  dec     r12d
0x180009f75  jmp     loc_180009E7D
0x180009f7a  mov     rdx, [rdx]
0x180009f7d  jmp     loc_180009EB2
0x180009f82  test    ecx, ecx
0x180009f84  jnz     loc_18000A2C5
0x180009f8a  lea     rax, [rsp+0D8h+var_A8]
0x180009f8f  cmp     [rsp+0D8h+var_A8.Flink], rax
0x180009f94  jnz     short loc_180009F9A
0x180009f96  mov     cl, 1
0x180009f98  jmp     short loc_180009FAA
0x180009f9a  mov     cl, bl
0x180009f9c  mov     rdi, [rsp+0D8h+var_A8.Blink]
0x180009fa1  add     rdi, 0FFFFFFFFFFFFFFD8h
0x180009fa5  mov     [rsp+0D8h+var_88], rdi
0x180009faa  lea     r14, [rsp+0D8h+var_90]
0x180009faf  test    cl, cl
0x180009fb1  cmovnz  r14, rbx
0x180009fb5  mov     [rsp+0D8h+var_48], r14
0x180009fbd  test    r8d, r8d
0x180009fc0  jnz     short loc_180009FD0
0x180009fc2  test    r9d, r9d
0x180009fc5  jnz     short loc_180009FD0
0x180009fc7  test    r14, r14
0x180009fca  jnz     loc_18000A164
0x180009fd0  mov     edx, ebx
0x180009fd2  test    r14, r14
0x180009fd5  jz      short loc_18000A046
0x180009fd7  mov     rcx, [rsp+0D8h+var_70.Flink]
0x180009fdc  lea     rax, [rsp+0D8h+var_70]
0x180009fe1  cmp     rcx, rax
0x180009fe4  jz      short loc_18000A046
0x180009fe6  lea     rdi, [rcx-28h]
0x180009fea  mov     [rsp+0D8h+var_88], rdi
0x180009fef  mov     eax, [rdi+10h]
0x180009ff2  cmp     [r14], eax
0x180009ff5  jnz     short loc_18000A000
0x180009ff7  mov     eax, [rdi+14h]
0x180009ffa  cmp     [r14+4], eax
0x180009ffe  jz      short loc_18000A005
0x18000a000  mov     rcx, [rcx]
0x18000a003  jmp     short loc_180009FDC
0x18000a005  mov     rax, [rcx]
0x18000a008  cmp     [rax+8], rcx
0x18000a00c  jnz     loc_18000A297
0x18000a012  mov     rdx, [rcx+8]
0x18000a016  cmp     [rdx], rcx
0x18000a019  jnz     loc_18000A297
0x18000a01f  mov     [rdx], rax
0x18000a022  mov     [rax+8], rdx
0x18000a026  mov     rcx, [rdi+20h]; lpAddress
0x18000a02a  test    rcx, rcx
0x18000a02d  jz      short loc_18000A041
0x18000a02f  xor     edx, edx; dwSize
0x18000a031  mov     r8d, 8000h; dwFreeType
0x18000a037  call    cs:__imp_VirtualFree
0x18000a03d  mov     [rdi+20h], rbx
0x18000a041  mov     edx, 1
0x18000a046  test    edx, edx
0x18000a048  jnz     loc_18000A0E8
0x18000a04e  mov     r9, r14; unsigned int *
0x18000a051  mov     r8d, [rsp+0D8h+arg_0]; unsigned int
0x18000a059  lea     rdx, [rsp+0D8h+var_60]; void **
0x18000a05e  lea     rcx, [rsp+0D8h+SectionHandle]; SectionHandle
0x18000a066  call    ?OpenDbgSection@@YAJPEAPEAX0KPEAK@Z; OpenDbgSection(void * *,void * *,ulong,ulong *)
0x18000a06b  mov     esi, eax
0x18000a06d  cmp     eax, 2
0x18000a070  jnz     short loc_18000A080
0x18000a072  test    r14, r14
0x18000a075  jz      loc_18000A358
0x18000a07b  jmp     loc_180009F72
0x18000a080  test    eax, eax
0x18000a082  jnz     loc_18000A358
0x18000a088  lea     ecx, [rax+38h]; unsigned __int64
0x18000a08b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a090  mov     rdi, rax
0x18000a093  test    rax, rax
0x18000a096  jnz     short loc_18000A0B2
0x18000a098  lea     esi, [rax+0Eh]
0x18000a09b  mov     rdx, [rsp+0D8h+var_60]; void *
0x18000a0a0  mov     rcx, [rsp+0D8h+SectionHandle]; void *
0x18000a0a8  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x18000a0ad  jmp     loc_18000A358
0x18000a0b2  mov     [rsp+0D8h+var_88], rdi
0x18000a0b7  mov     rax, [rsp+0D8h+SectionHandle]
0x18000a0bf  mov     [rdi], rax
0x18000a0c2  test    r14, r14
0x18000a0c5  jz      short loc_18000A0D3
0x18000a0c7  mov     eax, [r14]
0x18000a0ca  mov     [rdi+10h], eax
0x18000a0cd  mov     eax, [r14+4]
0x18000a0d1  jmp     short loc_18000A0D8
0x18000a0d3  mov     [rdi+10h], ebx
0x18000a0d6  mov     eax, ebx
0x18000a0d8  mov     [rdi+14h], eax
0x18000a0db  mov     rax, [rsp+0D8h+var_60]
0x18000a0e0  mov     [rdi+8], rax
0x18000a0e4  mov     [rdi+20h], rbx
0x18000a0e8  mov     rax, [rdi+8]
0x18000a0ec  mov     ecx, [rax+8]
0x18000a0ef  mov     dword ptr [rsp+0D8h+var_90], ecx
0x18000a0f3  mov     rax, [rdi+8]
0x18000a0f7  mov     ecx, [rax+0Ch]
0x18000a0fa  mov     dword ptr [rsp+0D8h+var_90+4], ecx
0x18000a0fe  lea     r14, [rsp+0D8h+var_90]
0x18000a103  mov     [rsp+0D8h+var_48], r14
0x18000a10b  mov     r15d, ebx
0x18000a10e  mov     [rsp+0D8h+var_98], ebx
0x18000a112  jmp     short loc_18000A13B
0x18000a114  mov     r15d, 1
0x18000a11a  mov     [rsp+0D8h+var_98], r15d
0x18000a11f  xor     ebx, ebx
0x18000a121  mov     r12d, [rsp+0D8h+arg_10]
0x18000a129  mov     r13d, [rsp+0D8h+var_80]
0x18000a12e  mov     rdi, [rsp+0D8h+var_88]
0x18000a133  mov     r14, [rsp+0D8h+var_48]
0x18000a13b  test    r15d, r15d
0x18000a13e  jz      loc_18000A288
0x18000a144  mov     rcx, rdi; void *
0x18000a147  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a14c  mov     rdx, [rsp+0D8h+var_60]; void *
0x18000a151  mov     rcx, [rsp+0D8h+SectionHandle]; void *
0x18000a159  call    ?CloseDbgSection@@YAXPEAX0@Z; CloseDbgSection(void *,void *)
0x18000a15e  mov     r13d, 1
0x18000a164  test    r13d, r13d
0x18000a167  jnz     loc_180009F72
0x18000a16d  mov     rsi, [rsp+0D8h+var_A8.Flink]
0x18000a172  mov     [rsp+0D8h+var_78], rsi
0x18000a177  lea     rax, [rsp+0D8h+var_A8]
0x18000a17c  cmp     rsi, rax
0x18000a17f  jz      loc_18000A277
0x18000a185  lea     rdi, [rsi-28h]
0x18000a189  mov     [rsp+0D8h+var_88], rdi
0x18000a18e  mov     r14, rdi
0x18000a191  cmp     [rdi+20h], rbx
0x18000a195  jnz     short loc_18000A1FA
0x18000a197  mov     rax, [rdi+8]
0x18000a19b  movzx   r15d, word ptr [rax+2]
0x18000a1a0  mov     eax, r15d
0x18000a1a3  imul    eax, [rsp+0D8h+var_50]
0x18000a1ab  mov     r13d, eax
0x18000a1ae  mov     r9d, 4; flProtect
0x18000a1b4  mov     r8d, 1000h; flAllocationType
0x18000a1ba  mov     edx, eax; dwSize
0x18000a1bc  xor     ecx, ecx; lpAddress
0x18000a1be  call    cs:__imp_VirtualAlloc
0x18000a1c4  mov     [rdi+20h], rax
0x18000a1c8  test    rax, rax
0x18000a1cb  jnz     short loc_18000A1DC
0x18000a1cd  lea     esi, [rax+0Eh]
0x18000a1d0  mov     [rsp+0D8h+var_40], esi
0x18000a1d7  jmp     loc_18000A358
0x18000a1dc  mov     r8, r13; Size
0x18000a1df  mov     rdx, [rdi+8]; Src
0x18000a1e3  mov     rcx, rax; void *
0x18000a1e6  call    memcpy_0
0x18000a1eb  mov     rax, [rdi+8]
0x18000a1ef  movsx   ecx, word ptr [rax+4]
0x18000a1f3  mov     [rdi+1Ch], ecx
0x18000a1f6  mov     [rdi+18h], r15d
0x18000a1fa  mov     r15d, ebx
0x18000a1fd  mov     [rsp+0D8h+var_98], ebx
0x18000a201  jmp     short loc_18000A225
0x18000a203  mov     r15d, 1
0x18000a209  mov     [rsp+0D8h+var_98], r15d
0x18000a20e  xor     ebx, ebx
0x18000a210  mov     r12d, [rsp+0D8h+arg_10]
0x18000a218  mov     rdi, [rsp+0D8h+var_88]
0x18000a21d  mov     rsi, [rsp+0D8h+var_78]
0x18000a222  mov     r14, rdi
0x18000a225  test    r15d, r15d
0x18000a228  jz      short loc_18000A26F
0x18000a22a  mov     rcx, [rdi+20h]; lpAddress
0x18000a22e  test    rcx, rcx
0x18000a231  jz      short loc_18000A245
0x18000a233  xor     edx, edx; dwSize
0x18000a235  mov     r8d, 8000h; dwFreeType
0x18000a23b  call    cs:__imp_VirtualFree
0x18000a241  mov     [rdi+20h], rbx
0x18000a245  mov     [rsp+0D8h+var_B8], r15d; int
0x18000a24a  mov     r9, rdi; struct tagOpenedDbgSection *
0x18000a24d  mov     r8, rsi; struct _LIST_ENTRY *
0x18000a250  lea     rdx, [rsp+0D8h+var_70]; struct _LIST_ENTRY *
0x18000a255  lea     rcx, [rsp+0D8h+var_A8]; struct _LIST_ENTRY *
0x18000a25a  call    ?InconsistencyDetected@@YAXPEAU_LIST_ENTRY@@00PEAUtagOpenedDbgSection@@H@Z; InconsistencyDetected(_LIST_ENTRY *,_LIST_ENTRY *,_LIST_ENTRY *,tagOpenedDbgSection *,int)
0x18000a25f  dec     r12d
0x18000a262  mov     rdi, r14
0x18000a265  mov     [rsp+0D8h+var_88], r14
0x18000a26a  jmp     loc_180009E7D
0x18000a26f  mov     rsi, [rsi]
0x18000a272  jmp     loc_18000A172
0x18000a277  mov     ecx, 1
0x18000a27c  mov     [rsp+0D8h+arg_18], ecx
0x18000a283  jmp     loc_180009E8E
0x18000a288  mov     rcx, [rsp+0D8h+var_A8.Blink]
0x18000a28d  lea     rax, [rsp+0D8h+var_A8]
0x18000a292  cmp     [rcx], rax
0x18000a295  jz      short loc_18000A29E
0x18000a297  mov     ecx, 3
0x18000a29c  int     29h; Win8: RtlFailFast(ecx)
0x18000a29e  lea     rax, [rdi+28h]
0x18000a2a2  lea     rdx, [rsp+0D8h+var_A8]
0x18000a2a7  mov     [rax], rdx
0x18000a2aa  mov     [rax+8], rcx
0x18000a2ae  mov     [rcx], rax
0x18000a2b1  mov     [rsp+0D8h+var_A8.Blink], rax
0x18000a2b6  mov     r9d, dword ptr [rsp+0D8h+var_90+4]
0x18000a2bb  mov     r8d, dword ptr [rsp+0D8h+var_90]
0x18000a2c0  jmp     loc_180009FBD
  ... truncated ...
```
