# SuCreatePoolEx(ushort const *,_SU_POOL_OBJECT * *,uint,_SP_DRIVE_INFO *,ulong *)

- ea: `0x140014f14`
- end: `0x1400151cd`
- name: `?SuCreatePoolEx@@YAHPEBGPEAPEAU_SU_POOL_OBJECT@@IPEAU_SP_DRIVE_INFO@@PEAK@Z`
- size: `697`
- prototype: `__int64 __fastcall(unsigned __int16 *, HLOCAL *, unsigned int, struct _SP_DRIVE_INFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400183b4`

## callees

- `0x140008190`
- `0x14000e018`
- `0x140014e74`
- `0x140014f14`
- `0x1400151d4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400150e7`
- `KERNEL32!LocalFree` at `0x14001519c`
- `KERNEL32!LocalFree` at `0x1400150e7`
- `KERNEL32!LocalFree` at `0x14001519c`
- `KERNEL32!SetLastError` at `0x140015127`
- `KERNEL32!SetLastError` at `0x1400151ad`
- `KERNEL32!SetLastError` at `0x140015127`
- `KERNEL32!SetLastError` at `0x1400151ad`
- `KERNEL32!GetLastError` at `0x140014fa3`
- `KERNEL32!GetLastError` at `0x14001512d`
- `KERNEL32!GetLastError` at `0x140015139`
- `KERNEL32!GetLastError` at `0x140015150`
- `KERNEL32!GetLastError` at `0x140014fa3`
- `KERNEL32!GetLastError` at `0x14001512d`
- `KERNEL32!GetLastError` at `0x140015139`
- `KERNEL32!GetLastError` at `0x140015150`

## pseudocode

```c
__int64 __fastcall SuCreatePoolEx(
        unsigned __int16 *a1,
        HLOCAL *a2,
        unsigned int a3,
        struct _SP_DRIVE_INFO *a4,
        unsigned int *a5)
{
  DWORD v5; // ebx
  HLOCAL v6; // r14
  unsigned int Drive; // edi
  __int64 v8; // r15
  struct _SU_POOL_OBJECT *p_hMem; // rcx
  unsigned int v11; // r12d
  DWORD LastError; // eax
  __int64 v13; // r12
  struct _SU_DRIVE_OBJECT *v14; // rsi
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *Flink; // rcx
  int v17; // r15d
  struct _LIST_ENTRY *v18; // rsi
  struct _LIST_ENTRY *v19; // rax
  unsigned int i; // edx
  __int64 v21; // r8
  char *v22; // rax
  DWORD v23; // eax
  DWORD v24; // ebx
  struct _LIST_ENTRY *v25; // rcx
  struct _LIST_ENTRY *v26; // rax
  struct _SU_DRIVE_OBJECT *v28; // [rsp+20h] [rbp-20h] BYREF
  HLOCAL v29; // [rsp+28h] [rbp-18h] BYREF
  struct _LIST_ENTRY hMem; // [rsp+30h] [rbp-10h] BYREF

  v5 = 0;
  v6 = 0;
  hMem.Blink = &hMem;
  Drive = 0;
  v29 = 0;
  v8 = 0;
  v28 = 0;
  p_hMem = (struct _SU_POOL_OBJECT *)&hMem;
  hMem.Flink = &hMem;
  if ( !a3 )
    goto LABEL_41;
  v11 = a3;
  do
  {
    LastError = a5[v8];
    if ( LastError )
    {
      if ( v5 )
        LastError = v5;
LABEL_6:
      v5 = LastError;
      goto LABEL_12;
    }
    v13 = 3120LL * (unsigned int)v8;
    Drive = SuGetDrive(p_hMem, (struct _GUID *)((char *)a4 + v13 + 24), &v28);
    if ( Drive )
    {
      v14 = v28;
      StringCchCopyW((unsigned __int16 *)v28 + 60, 0x100u, (size_t *)((char *)a4 + v13 + 48));
      StringCchCopyW((unsigned __int16 *)v14 + 316, 0x400u, (size_t *)((char *)a4 + v13 + 560));
      *((_DWORD *)v14 + 714) = *(_DWORD *)((char *)a4 + v13 + 2784);
      Blink = hMem.Blink;
      if ( hMem.Blink->Flink != &hMem )
LABEL_49:
        __fastfail(3u);
      v11 = a3;
      p_hMem = (struct _SU_POOL_OBJECT *)&hMem;
      *(_QWORD *)v14 = &hMem;
      *((_QWORD *)v14 + 1) = Blink;
      Blink->Flink = (struct _LIST_ENTRY *)v14;
      hMem.Blink = (struct _LIST_ENTRY *)v14;
      v28 = 0;
    }
    else
    {
      LastError = GetLastError();
      p_hMem = (struct _SU_POOL_OBJECT *)a5;
      v11 = a3;
      a5[v8] = LastError;
      if ( !v5 )
        goto LABEL_6;
    }
LABEL_12:
    v8 = (unsigned int)(v8 + 1);
  }
  while ( (unsigned int)v8 < v11 );
  if ( hMem.Flink == &hMem )
  {
LABEL_41:
    Drive = 0;
    v23 = GetLastError();
    goto LABEL_42;
  }
  while ( (unsigned int)v6 < 2 )
  {
    Drive = SuCreatePool2(a1, (struct _SU_POOL_OBJECT **)&v29, &hMem);
    if ( Drive )
      goto LABEL_40;
    Flink = hMem.Flink;
    v17 = 0;
    if ( hMem.Flink != &hMem )
    {
      do
      {
        v18 = Flink->Flink;
        if ( LODWORD(Flink[1].Flink) )
        {
          if ( v18->Blink != Flink )
            goto LABEL_49;
          v19 = Flink->Blink;
          if ( v19->Flink != Flink )
            goto LABEL_49;
          v19->Flink = v18;
          v17 = 1;
          v18->Blink = v19;
          for ( i = 0; i < v11; ++i )
          {
            v21 = 3120LL * i;
            v22 = (char *)Flink[3].Blink - *(_QWORD *)((char *)a4 + v21 + 24);
            if ( !v22 )
              v22 = (char *)Flink[4].Flink - *(_QWORD *)((char *)a4 + v21 + 32);
            if ( !v22 )
            {
              if ( !v5 )
                v5 = (DWORD)Flink[1].Flink;
              a5[i] = (unsigned int)Flink[1].Flink;
              break;
            }
          }
          LocalFree(Flink);
        }
        Flink = v18;
      }
      while ( v18 != &hMem );
      Flink = hMem.Flink;
    }
    if ( Flink == &hMem || !v17 )
    {
      Drive = 0;
      goto LABEL_37;
    }
    LODWORD(v6) = (_DWORD)v6 + 1;
  }
  if ( Drive )
  {
LABEL_40:
    v24 = GetLastError();
    *a2 = v29;
    goto LABEL_45;
  }
LABEL_37:
  if ( !v5 )
    v5 = 15;
  SetLastError(v5);
  v23 = GetLastError();
  v6 = v29;
LABEL_42:
  v24 = v23;
  if ( v6 )
    SuCreatePool_CleanupPool(v6);
  *a2 = 0;
LABEL_45:
  while ( 1 )
  {
    v25 = hMem.Flink;
    if ( hMem.Flink == &hMem )
      break;
    if ( hMem.Flink->Blink != &hMem )
      goto LABEL_49;
    v26 = hMem.Flink->Flink;
    if ( hMem.Flink->Flink->Blink != hMem.Flink )
      goto LABEL_49;
    hMem.Flink = hMem.Flink->Flink;
    v26->Blink = &hMem;
    LocalFree(v25);
  }
  SetLastError(v24);
  return Drive;
}

```

## disassembly

```asm
0x140014f14  mov     rax, rsp
0x140014f17  mov     [rax+20h], rbx
0x140014f1b  mov     [rax+18h], r8d
0x140014f1f  mov     [rax+10h], rdx
0x140014f23  mov     [rax+8], rcx
0x140014f27  push    rbp
0x140014f28  push    rsi
0x140014f29  push    rdi
0x140014f2a  push    r12
0x140014f2c  push    r13
0x140014f2e  push    r14
0x140014f30  push    r15
0x140014f32  mov     rbp, rsp
0x140014f35  sub     rsp, 40h
0x140014f39  lea     rcx, [rbp+hMem]
0x140014f3d  xor     ebx, ebx
0x140014f3f  xor     r14d, r14d
0x140014f42  mov     [rbp+var_8], rcx
0x140014f46  xor     edi, edi
0x140014f48  mov     [rbp+var_18], r14
0x140014f4c  xor     r15d, r15d
0x140014f4f  mov     [rbp+var_20], rbx
0x140014f53  lea     rcx, [rbp+hMem]; struct _SU_POOL_OBJECT *
0x140014f57  mov     r13, r9
0x140014f5a  mov     [rbp+hMem], rcx
0x140014f5e  test    r8d, r8d
0x140014f61  jz      loc_14001514E
0x140014f67  mov     r12d, [rbp+arg_10]
0x140014f6b  mov     rax, [rbp+arg_20]
0x140014f6f  mov     esi, r15d
0x140014f72  mov     eax, [rax+r15*4]
0x140014f76  test    eax, eax
0x140014f78  jz      short loc_140014F86
0x140014f7a  test    ebx, ebx
0x140014f7c  cmovnz  eax, ebx
0x140014f7f  mov     ebx, eax
0x140014f81  jmp     loc_140015029
0x140014f86  imul    r12, rsi, 0C30h
0x140014f8d  lea     rdx, [r13+18h]
0x140014f91  add     rdx, r12; struct _GUID *
0x140014f94  lea     r8, [rbp+var_20]; struct _SU_DRIVE_OBJECT **
0x140014f98  call    ?SuGetDrive@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@PEAPEAU_SU_DRIVE_OBJECT@@@Z; SuGetDrive(_SU_POOL_OBJECT *,_GUID *,_SU_DRIVE_OBJECT * *)
0x140014f9d  mov     edi, eax
0x140014f9f  test    eax, eax
0x140014fa1  jnz     short loc_140014FBB
0x140014fa3  call    cs:__imp_GetLastError
0x140014fa9  mov     rcx, [rbp+arg_20]
0x140014fad  mov     r12d, [rbp+arg_10]
0x140014fb1  mov     [rcx+r15*4], eax
0x140014fb5  test    ebx, ebx
0x140014fb7  jnz     short loc_140015029
0x140014fb9  jmp     short loc_140014F7F
0x140014fbb  mov     rsi, [rbp+var_20]
0x140014fbf  lea     r8, [r13+30h]
0x140014fc3  add     r8, r12; unsigned __int16 *
0x140014fc6  mov     edx, 100h; unsigned __int64
0x140014fcb  lea     rcx, [rsi+78h]; unsigned __int16 *
0x140014fcf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140014fd4  lea     r8, [r13+230h]
0x140014fdb  mov     edx, 400h; unsigned __int64
0x140014fe0  add     r8, r12; unsigned __int16 *
0x140014fe3  lea     rcx, [rsi+278h]; unsigned __int16 *
0x140014fea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140014fef  mov     r11d, [r12+r13+0AE0h]
0x140014ff7  lea     rcx, [rbp+hMem]
0x140014ffb  mov     [rsi+0B28h], r11d
0x140015002  mov     rax, [rbp+var_8]
0x140015006  cmp     [rax], rcx
0x140015009  jnz     loc_1400151A4
0x14001500f  mov     r12d, [rbp+arg_10]
0x140015013  lea     rcx, [rbp+hMem]
0x140015017  mov     [rsi], rcx
0x14001501a  mov     [rsi+8], rax
0x14001501e  mov     [rax], rsi
0x140015021  mov     [rbp+var_8], rsi
0x140015025  mov     [rbp+var_20], r14
0x140015029  inc     r15d
0x14001502c  cmp     r15d, r12d
0x14001502f  jb      loc_140014F6B
0x140015035  lea     rax, [rbp+hMem]
0x140015039  cmp     [rbp+hMem], rax
0x14001503d  jz      loc_14001514E
0x140015043  cmp     r14d, 2
0x140015047  jnb     loc_140015117
0x14001504d  mov     rcx, [rbp+arg_0]; unsigned __int16 *
0x140015051  lea     r8, [rbp+hMem]; struct _LIST_ENTRY *
0x140015055  lea     rdx, [rbp+var_18]; struct _SU_POOL_OBJECT **
0x140015059  call    SuCreatePool2
0x14001505e  mov     edi, eax
0x140015060  test    eax, eax
0x140015062  jnz     loc_140015139
0x140015068  mov     rcx, [rbp+hMem]; hMem
0x14001506c  lea     rax, [rbp+hMem]
0x140015070  xor     r15d, r15d
0x140015073  cmp     rcx, rax
0x140015076  jz      loc_1400150FD
0x14001507c  cmp     dword ptr [rcx+10h], 0
0x140015080  mov     rsi, [rcx]
0x140015083  jz      short loc_1400150ED
0x140015085  cmp     [rsi+8], rcx
0x140015089  jnz     loc_1400151A4
0x14001508f  mov     rax, [rcx+8]
0x140015093  cmp     [rax], rcx
0x140015096  jnz     loc_1400151A4
0x14001509c  mov     [rax], rsi
0x14001509f  mov     r15d, 1
0x1400150a5  mov     [rsi+8], rax
0x1400150a9  xor     edx, edx
0x1400150ab  cmp     edx, r12d
0x1400150ae  jnb     short loc_1400150E7
0x1400150b0  mov     rax, [rcx+38h]
0x1400150b4  mov     r9d, edx
0x1400150b7  imul    r8, r9, 0C30h
0x1400150be  sub     rax, [r8+r13+18h]
0x1400150c3  jnz     short loc_1400150CE
0x1400150c5  mov     rax, [rcx+40h]
0x1400150c9  sub     rax, [r8+r13+20h]
0x1400150ce  test    rax, rax
0x1400150d1  jz      short loc_1400150D7
0x1400150d3  inc     edx
0x1400150d5  jmp     short loc_1400150AB
0x1400150d7  mov     eax, [rcx+10h]
0x1400150da  test    ebx, ebx
0x1400150dc  mov     rdx, [rbp+arg_20]
0x1400150e0  cmovz   ebx, eax
0x1400150e3  mov     [rdx+r9*4], eax
0x1400150e7  call    cs:__imp_LocalFree
0x1400150ed  lea     rax, [rbp+hMem]
0x1400150f1  mov     rcx, rsi
0x1400150f4  cmp     rsi, rax
0x1400150f7  jnz     short loc_14001507C
0x1400150f9  mov     rcx, [rbp+hMem]
0x1400150fd  lea     rax, [rbp+hMem]
0x140015101  cmp     rcx, rax
0x140015104  jz      short loc_140015113
0x140015106  test    r15d, r15d
0x140015109  jz      short loc_140015113
0x14001510b  inc     r14d
0x14001510e  jmp     loc_140015043
0x140015113  xor     edi, edi
0x140015115  jmp     short loc_14001511B
0x140015117  test    edi, edi
0x140015119  jnz     short loc_140015139
0x14001511b  mov     eax, 0Fh
0x140015120  test    ebx, ebx
0x140015122  cmovz   ebx, eax
0x140015125  mov     ecx, ebx; dwErrCode
0x140015127  call    cs:__imp_SetLastError
0x14001512d  call    cs:__imp_GetLastError
0x140015133  mov     r14, [rbp+var_18]
0x140015137  jmp     short loc_140015156
0x140015139  call    cs:__imp_GetLastError
0x14001513f  mov     rcx, [rbp+arg_8]
0x140015143  mov     ebx, eax
0x140015145  mov     rax, [rbp+var_18]
0x140015149  mov     [rcx], rax
0x14001514c  jmp     short loc_140015170
0x14001514e  xor     edi, edi
0x140015150  call    cs:__imp_GetLastError
0x140015156  mov     ebx, eax
0x140015158  test    r14, r14
0x14001515b  jz      short loc_140015165
0x14001515d  mov     rcx, r14; hMem
0x140015160  call    SuCreatePool_CleanupPool
0x140015165  mov     rcx, [rbp+arg_8]
0x140015169  mov     qword ptr [rcx], 0
0x140015170  mov     rcx, [rbp+hMem]; hMem
0x140015174  lea     rax, [rbp+hMem]
0x140015178  cmp     rcx, rax
0x14001517b  jz      short loc_1400151AB
0x14001517d  lea     rax, [rbp+hMem]
0x140015181  cmp     [rcx+8], rax
0x140015185  jnz     short loc_1400151A4
0x140015187  mov     rax, [rcx]
0x14001518a  cmp     [rax+8], rcx
0x14001518e  jnz     short loc_1400151A4
0x140015190  lea     rdx, [rbp+hMem]
0x140015194  mov     [rbp+hMem], rax
0x140015198  mov     [rax+8], rdx
0x14001519c  call    cs:__imp_LocalFree
0x1400151a2  jmp     short loc_140015170
0x1400151a4  mov     ecx, 3
0x1400151a9  int     29h; Win8: RtlFailFast(ecx)
0x1400151ab  mov     ecx, ebx; dwErrCode
0x1400151ad  call    cs:__imp_SetLastError
0x1400151b3  mov     rbx, [rsp+40h+arg_18]
0x1400151bb  mov     eax, edi
0x1400151bd  add     rsp, 40h
0x1400151c1  pop     r15
0x1400151c3  pop     r14
0x1400151c5  pop     r13
0x1400151c7  pop     r12
0x1400151c9  pop     rdi
0x1400151ca  pop     rsi
0x1400151cb  pop     rbp
0x1400151cc  retn
```
