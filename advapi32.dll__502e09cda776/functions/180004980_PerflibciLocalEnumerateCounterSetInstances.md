# PerflibciLocalEnumerateCounterSetInstances

- ea: `0x180004980`
- end: `0x180004eba`
- name: `PerflibciLocalEnumerateCounterSetInstances`
- size: `1338`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *Buf1, struct _PERF_INSTANCE_HEADER *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004830`

## callees

- `0x180002674`
- `0x180002e84`
- `0x18000398c`
- `0x180003d58`
- `0x180004980`
- `0x180006420`
- `0x180006ad4`
- `0x18004165c`
- `0x180072042`
- `0x18007205a`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180004cd2`
- `msvcrt!wcsnlen` at `0x180004cd2`
- `KERNEL32!LocalFree` at `0x180004ab4`
- `KERNEL32!LocalFree` at `0x180004ba7`
- `KERNEL32!LocalFree` at `0x180004c54`
- `KERNEL32!LocalFree` at `0x180004ab4`
- `KERNEL32!LocalFree` at `0x180004ba7`
- `KERNEL32!LocalFree` at `0x180004c54`
- `KERNEL32!GetComputerNameW` at `0x180004a89`
- `KERNEL32!GetComputerNameW` at `0x180004a89`

## pseudocode

```c
DWORD __fastcall PerflibciLocalEnumerateCounterSetInstances(
        unsigned __int16 *a1,
        void *Buf1,
        struct _PERF_INSTANCE_HEADER *a3,
        unsigned int a4,
        unsigned int *a5)
{
  DWORD result; // eax
  int v10; // r14d
  __int64 CounterSet; // rax
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // rax
  DWORD v15; // eax
  unsigned __int64 v16; // rbp
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  int v19; // edx
  bool v20; // zf
  unsigned int *v21; // rcx
  unsigned int v22; // edx
  unsigned int v23; // ebx
  unsigned int v24; // ebp
  unsigned int v25; // edx
  int v26; // eax
  int v27; // eax
  unsigned int *v28; // rdi
  __int64 v29; // r10
  unsigned int v30; // eax
  __int64 v31; // rcx
  unsigned int v32; // ebp
  unsigned int v33; // r9d
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int16 *v36; // rax
  unsigned int v37; // edx
  unsigned int v38; // ecx
  unsigned int v39; // edx
  unsigned int v40; // r10d
  const WCHAR *v41; // r9
  __int64 v42; // rcx
  _WORD *v43; // rdx
  __int64 v44; // r8
  _WORD *v45; // rcx
  int v46; // [rsp+20h] [rbp-78h]
  unsigned int Src; // [rsp+40h] [rbp-58h]
  unsigned __int16 *Srca; // [rsp+40h] [rbp-58h]
  unsigned int v49; // [rsp+48h] [rbp-50h]
  DWORD nSize; // [rsp+4Ch] [rbp-4Ch] BYREF
  unsigned int v51; // [rsp+50h] [rbp-48h] BYREF
  int v52; // [rsp+54h] [rbp-44h]
  unsigned int v53; // [rsp+58h] [rbp-40h]
  unsigned int v54; // [rsp+5Ch] [rbp-3Ch]
  HLOCAL hMem; // [rsp+60h] [rbp-38h] BYREF
  int v56; // [rsp+68h] [rbp-30h]
  int v57; // [rsp+A8h] [rbp+10h]

  v57 = (int)Buf1;
  hMem = 0;
  nSize = 0;
  v51 = 0;
  result = PerflibciEnsureCounterSetList();
  v10 = result;
  if ( !result )
  {
    CounterSet = PerflibciCreateOrFindCounterSet(Buf1, 0, 0, 0, 0);
    v12 = CounterSet;
    if ( !CounterSet )
      return 4200;
    if ( *(_DWORD *)(*(_QWORD *)(CounterSet + 16) + 32LL) == 1 )
      return PerfpEnumerateKernelInstances((struct PERFLIBCI_COUNTERSET_NODE *)CounterSet, a3, a4, a5);
    *a5 = 0;
    if ( a4 )
    {
      if ( a3 )
      {
        LOBYTE(a3->Size) = 0;
        *((_BYTE *)a3 + a4 - 1) = 0;
      }
      else
      {
        v10 = 87;
      }
    }
    v13 = -1;
    if ( a1 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a1[v14] );
      v15 = v14 + 1;
    }
    else
    {
      v15 = 261;
    }
    nSize = v15;
    v16 = 2LL * v15;
    if ( !is_mul_ok(v15, 2u) )
      v16 = -1;
    v17 = (unsigned __int16 *)operator new(v16, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      v10 = 14;
      goto LABEL_16;
    }
    memset_0(v17, 0, v16);
    if ( a1 && *a1 )
      StringCchCopyW(v18, nSize, a1);
    else
      GetComputerNameW(v18, &nSize);
    do
      v20 = v18[++v13] == 0;
    while ( !v20 );
    if ( v10 )
      goto LABEL_16;
    v51 = 0x2000;
    v10 = PerfpSendStateLessNotification(v57, v19, (_DWORD)v18, 2 * (int)v13 + 2, (__int64)&hMem, (__int64)&v51);
    if ( v10 )
      goto LABEL_16;
    v21 = (unsigned int *)hMem;
    v22 = 0;
    v23 = 0;
    Src = 0;
    v49 = 0;
    v24 = 8;
    while ( 1 )
    {
      v54 = v22;
      v53 = v24;
      if ( v22 >= *v21 || v24 >= v51 )
        break;
      v28 = (unsigned int *)((char *)v21 + v24);
      v29 = *v28;
      v56 = v29;
      if ( (unsigned int)v29 >= 0x20 && !v28[3] )
      {
        v30 = v28[6];
        if ( (*(_BYTE *)(v12 + 88) & 2) != 0 )
        {
          if ( v30 == -1 )
            goto LABEL_46;
          if ( v30 )
          {
            LODWORD(v31) = v29;
            if ( (unsigned __int64)(v29 - 8) > 0x20 )
            {
              v32 = Src;
              v33 = 32;
              v52 = 32;
              v34 = 32;
              do
              {
                v35 = *(unsigned int *)((char *)v28 + v34);
                Srca = (unsigned __int16 *)((char *)v28 + v34);
                if ( (unsigned int)v35 > (unsigned int)v31 - v33 || (unsigned int)v35 < 0x10 )
                  break;
                if ( (unsigned int)((unsigned __int64)(v35 - 8) >> 1) == wcsnlen(
                                                                           (const wchar_t *)((char *)v28 + v34 + 8),
                                                                           (unsigned int)((unsigned __int64)(v35 - 8) >> 1)) )
                {
                  v23 = v49;
                  break;
                }
                v23 = v49;
                v20 = PerflibciFindInstance(
                        (struct PERFLIBCI_COUNTERSET_NODE *)v12,
                        Srca + 4,
                        *((_DWORD *)Srca + 1),
                        v28[7],
                        v46) == 0;
                v36 = Srca;
                if ( !v20 )
                {
                  v23 = ++v49;
                  if ( (*(_BYTE *)(v12 + 88) & 2) != 0 )
                  {
                    if ( a3
                      && (v37 = *(_DWORD *)Srca, v38 = *(_DWORD *)Srca + v32, v32 <= v38)
                      && v37 <= v38
                      && v38 <= a4 )
                    {
                      memcpy_0((char *)a3 + v32, Srca, v37);
                      v36 = Srca;
                    }
                    else
                    {
                      v10 = 8;
                    }
                    v32 += *(_DWORD *)v36;
                  }
                }
                v33 = *(_DWORD *)v36 + v52;
                v31 = *v28;
                v34 = v33;
                v52 = v33;
              }
              while ( v33 < (unsigned __int64)(v31 - 8) );
              v22 = v54;
              LODWORD(v29) = v56;
              Src = v32;
              v24 = v53;
            }
            v21 = (unsigned int *)hMem;
          }
        }
        else if ( v30 == -1 )
        {
          v49 = ++v23;
        }
        else if ( v30 )
        {
LABEL_46:
          v10 = 4211;
          break;
        }
      }
      v24 += v29;
      ++v22;
    }
    if ( *(_DWORD *)(v12 + 88) != 6 || !v23 )
    {
      v25 = Src;
      goto LABEL_24;
    }
    ++v23;
    if ( a3 )
    {
      v39 = Src;
      v40 = Src + 24;
      if ( Src < Src + 24 && v40 >= 0x18 && v40 <= a4 )
      {
        *(struct _PERF_INSTANCE_HEADER *)((char *)a3 + Src) = (struct _PERF_INSTANCE_HEADER)24LL;
        v41 = L"_Total";
        v42 = 2147483646;
        v43 = (_WORD *)((char *)&a3[1] + Src);
        v44 = 7;
        do
        {
          if ( !v42 )
            break;
          if ( !*v41 )
            break;
          *v43++ = *v41++;
          --v42;
          --v44;
        }
        while ( v44 );
        v45 = v43 - 1;
        if ( v44 )
          v45 = v43;
        v25 = Src + 24;
        *v45 = 0;
        v21 = (unsigned int *)hMem;
LABEL_24:
        if ( (v10 & 0xFFFFFFF7) == 0 )
        {
          v26 = *(_DWORD *)(v12 + 88);
          if ( v26 == 6 )
          {
LABEL_26:
            v27 = v10;
            if ( !v23 )
              v27 = 4201;
            v10 = v27;
            *a5 = v25;
            goto LABEL_29;
          }
          if ( v26 )
          {
            if ( v26 == 2 )
              goto LABEL_26;
            if ( v26 != 4 && v26 != 12 )
            {
LABEL_44:
              v10 = 4211;
              LocalFree(v21);
              goto LABEL_16;
            }
          }
          else if ( v23 > 1 )
          {
            goto LABEL_44;
          }
          if ( v23 )
            *a5 = 0;
          else
            v10 = 4201;
        }
LABEL_29:
        LocalFree(v21);
LABEL_16:
        LocalFree(v18);
        return v10;
      }
    }
    else
    {
      v39 = Src;
    }
    v10 = 8;
    v25 = v39 + 24;
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x180004980  mov     [rsp+arg_18], rbx
0x180004985  mov     [rsp+arg_8], rdx
0x18000498a  push    rsi
0x18000498b  push    rdi
0x18000498c  push    r12
0x18000498e  push    r13
0x180004990  push    r14
0x180004992  sub     rsp, 70h
0x180004996  xor     esi, esi
0x180004998  mov     r13d, r9d
0x18000499b  mov     [rsp+98h+hMem], rsi
0x1800049a0  mov     r12, r8
0x1800049a3  mov     [rsp+98h+nSize], esi
0x1800049a7  mov     rdi, rdx
0x1800049aa  mov     [rsp+98h+var_48], esi
0x1800049ae  mov     rbx, rcx
0x1800049b1  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x1800049b6  mov     r14d, eax
0x1800049b9  test    eax, eax
0x1800049bb  jnz     loc_180004AD3
0x1800049c1  mov     [rsp+98h+var_68], esi; int
0x1800049c5  xor     r9d, r9d
0x1800049c8  mov     [rsp+98h+var_70], si; __int16
0x1800049cd  xor     r8d, r8d
0x1800049d0  xor     edx, edx; Src
0x1800049d2  mov     [rsp+98h+var_78], rsi; void *
0x1800049d7  mov     rcx, rdi; Buf1
0x1800049da  mov     [rsp+98h+arg_10], r15
0x1800049e2  call    PerflibciCreateOrFindCounterSet
0x1800049e7  mov     r15, rax
0x1800049ea  test    rax, rax
0x1800049ed  jz      loc_180004E45
0x1800049f3  mov     rax, [rax+10h]
0x1800049f7  cmp     dword ptr [rax+20h], 1
0x1800049fb  jz      loc_180004AE9
0x180004a01  mov     rax, [rsp+98h+arg_20]
0x180004a09  mov     [rsp+98h+arg_0], rbp
0x180004a11  mov     [rax], esi
0x180004a13  test    r13d, r13d
0x180004a16  jnz     loc_180004BD6
0x180004a1c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180004a23  test    rbx, rbx
0x180004a26  jz      loc_180004E4F
0x180004a2c  mov     rax, rdi
0x180004a2f  nop
0x180004a30  inc     rax
0x180004a33  cmp     [rbx+rax*2], si
0x180004a37  jnz     short loc_180004A30
0x180004a39  inc     eax
0x180004a3b  mov     ecx, eax
0x180004a3d  mov     [rsp+98h+nSize], eax
0x180004a41  mov     eax, 2
0x180004a46  mul     rcx
0x180004a49  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a50  mov     rbp, rax
0x180004a53  cmovb   rbp, rdi
0x180004a57  mov     rcx, rbp; unsigned __int64
0x180004a5a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004a5f  mov     rsi, rax
0x180004a62  test    rax, rax
0x180004a65  jz      loc_180004E2F
0x180004a6b  mov     r8, rbp; Size
0x180004a6e  xor     edx, edx; Val
0x180004a70  mov     rcx, rax; void *
0x180004a73  call    memset_0
0x180004a78  test    rbx, rbx
0x180004a7b  jnz     loc_180004BB8
0x180004a81  lea     rdx, [rsp+98h+nSize]; nSize
0x180004a86  mov     rcx, rsi; lpBuffer
0x180004a89  call    cs:__imp_GetComputerNameW
0x180004a90  nop     dword ptr [rax+rax+00h]
0x180004a95  nop     word ptr [rax+rax+00000000h]
0x180004aa0  cmp     word ptr [rsi+rdi*2+2], 0
0x180004aa6  lea     rdi, [rdi+1]
0x180004aaa  jnz     short loc_180004AA0
0x180004aac  test    r14d, r14d
0x180004aaf  jz      short loc_180004B01
0x180004ab1  mov     rcx, rsi; hMem
0x180004ab4  call    cs:__imp_LocalFree
0x180004abb  nop     dword ptr [rax+rax+00h]
0x180004ac0  mov     rbp, [rsp+98h+arg_0]
0x180004ac8  mov     eax, r14d
0x180004acb  mov     r15, [rsp+98h+arg_10]
0x180004ad3  mov     rbx, [rsp+98h+arg_18]
0x180004adb  add     rsp, 70h
0x180004adf  pop     r14
0x180004ae1  pop     r13
0x180004ae3  pop     r12
0x180004ae5  pop     rdi
0x180004ae6  pop     rsi
0x180004ae7  retn
0x180004ae9  mov     r9, [rsp+98h+arg_20]; unsigned int *
0x180004af1  mov     r8d, r13d; unsigned int
0x180004af4  mov     rdx, r12; struct _PERF_INSTANCE_HEADER *
0x180004af7  mov     rcx, r15; struct PERFLIBCI_COUNTERSET_NODE *
0x180004afa  call    ?PerfpEnumerateKernelInstances@@YAKPEAUPERFLIBCI_COUNTERSET_NODE@@PEAU_PERF_INSTANCE_HEADER@@KPEAK@Z; PerfpEnumerateKernelInstances(PERFLIBCI_COUNTERSET_NODE *,_PERF_INSTANCE_HEADER *,ulong,ulong *)
0x180004aff  jmp     short loc_180004ACB
0x180004b01  mov     rcx, [rsp+98h+arg_8]
0x180004b09  lea     rax, [rsp+98h+var_48]
0x180004b0e  mov     qword ptr [rsp+98h+var_70], rax
0x180004b13  lea     r9d, ds:2[rdi*2]
0x180004b1b  lea     rax, [rsp+98h+hMem]
0x180004b20  mov     [rsp+98h+var_48], 2000h
0x180004b28  mov     r8, rsi
0x180004b2b  mov     [rsp+98h+var_78], rax; int
0x180004b30  call    PerfpSendStateLessNotification
0x180004b35  mov     r14d, eax
0x180004b38  test    eax, eax
0x180004b3a  jnz     loc_180004AB1
0x180004b40  mov     rcx, [rsp+98h+hMem]; hMem
0x180004b45  xor     edx, edx
0x180004b47  xor     ebx, ebx
0x180004b49  mov     dword ptr [rsp+98h+Src], edx
0x180004b4d  mov     [rsp+98h+var_50], ebx
0x180004b51  mov     ebp, 8
0x180004b56  mov     [rsp+98h+var_3C], edx
0x180004b5a  mov     [rsp+98h+var_40], ebp
0x180004b5e  cmp     edx, [rcx]
0x180004b60  jb      loc_180004BF7
0x180004b66  cmp     dword ptr [r15+58h], 6
0x180004b6b  jz      loc_180004D93
0x180004b71  mov     edx, dword ptr [rsp+98h+Src]
0x180004b75  test    r14d, 0FFFFFFF7h
0x180004b7c  jnz     short loc_180004BA7
0x180004b7e  mov     eax, [r15+58h]
0x180004b82  cmp     eax, 6
0x180004b85  jnz     loc_180004C3D
0x180004b8b  mov     eax, r14d
0x180004b8e  test    ebx, ebx
0x180004b90  mov     r14d, 1069h
0x180004b96  cmovz   eax, r14d
0x180004b9a  mov     r14d, eax
0x180004b9d  mov     rax, [rsp+98h+arg_20]
0x180004ba5  mov     [rax], edx
0x180004ba7  call    cs:__imp_LocalFree
0x180004bae  nop     dword ptr [rax+rax+00h]
0x180004bb3  jmp     loc_180004AB1
0x180004bb8  cmp     word ptr [rbx], 0
0x180004bbc  jz      loc_180004A81
0x180004bc2  mov     edx, [rsp+98h+nSize]; unsigned __int64
0x180004bc6  mov     r8, rbx; unsigned __int16 *
0x180004bc9  mov     rcx, rsi; unsigned __int16 *
0x180004bcc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004bd1  jmp     loc_180004AA0
0x180004bd6  test    r12, r12
0x180004bd9  jnz     short loc_180004BE6
0x180004bdb  mov     r14d, 57h ; 'W'
0x180004be1  jmp     loc_180004A1C
0x180004be6  lea     eax, [r13-1]
0x180004bea  mov     [r12], sil
0x180004bee  mov     [rax+r12], sil
0x180004bf2  jmp     loc_180004A1C
0x180004bf7  cmp     ebp, [rsp+98h+var_48]
0x180004bfb  jnb     loc_180004B66
0x180004c01  mov     edi, ebp
0x180004c03  add     rdi, rcx
0x180004c06  mov     r10d, [rdi]
0x180004c09  mov     [rsp+98h+var_30], r10d
0x180004c0e  cmp     r10d, 20h ; ' '
0x180004c12  jb      short loc_180004C33
0x180004c14  cmp     dword ptr [rdi+0Ch], 0
0x180004c18  jnz     short loc_180004C33
0x180004c1a  test    byte ptr [r15+58h], 2
0x180004c1f  mov     eax, [rdi+18h]
0x180004c22  jnz     short loc_180004C65
0x180004c24  cmp     eax, 0FFFFFFFFh
0x180004c27  jnz     loc_180004E59
0x180004c2d  inc     ebx
0x180004c2f  mov     [rsp+98h+var_50], ebx
0x180004c33  add     ebp, r10d
0x180004c36  inc     edx
0x180004c38  jmp     loc_180004B56
0x180004c3d  test    eax, eax
0x180004c3f  jnz     loc_180004E81
0x180004c45  cmp     ebx, 1
0x180004c48  jbe     loc_180004E98
0x180004c4e  mov     r14d, 1073h
0x180004c54  call    cs:__imp_LocalFree
0x180004c5b  nop     dword ptr [rax+rax+00h]
0x180004c60  jmp     loc_180004AB1
0x180004c65  cmp     eax, 0FFFFFFFFh
0x180004c68  jnz     short loc_180004C75
0x180004c6a  mov     r14d, 1073h
0x180004c70  jmp     loc_180004B66
0x180004c75  test    eax, eax
0x180004c77  jz      short loc_180004C33
0x180004c79  lea     rax, [r10-8]
0x180004c7d  mov     rcx, r10
0x180004c80  cmp     rax, 20h ; ' '
0x180004c84  jbe     loc_180004D89
0x180004c8a  mov     ebp, dword ptr [rsp+98h+Src]
0x180004c8e  mov     r9d, 20h ; ' '
0x180004c94  mov     [rsp+98h+var_44], r9d
0x180004c99  mov     edx, r9d
0x180004c9c  nop     dword ptr [rax+00h]
0x180004ca0  mov     r8d, [rdx+rdi]
0x180004ca4  lea     rax, [rdx+rdi]
0x180004ca8  sub     ecx, r9d
0x180004cab  mov     [rsp+98h+Src], rax
0x180004cb0  cmp     r8d, ecx
0x180004cb3  ja      loc_180004D78
0x180004cb9  cmp     r8d, 10h
0x180004cbd  jb      loc_180004D78
0x180004cc3  lea     rcx, [rax+8]; Source
0x180004cc7  lea     rax, [r8-8]
0x180004ccb  shr     rax, 1
0x180004cce  mov     edx, eax; MaxCount
0x180004cd0  mov     ebx, eax
0x180004cd2  call    cs:__imp_wcsnlen
0x180004cd9  nop     dword ptr [rax+rax+00h]
0x180004cde  cmp     rbx, rax
0x180004ce1  jz      loc_180004E66
0x180004ce7  mov     rax, [rsp+98h+Src]
0x180004cec  mov     rcx, r15; struct PERFLIBCI_COUNTERSET_NODE *
0x180004cef  mov     r9d, [rdi+1Ch]; unsigned int
0x180004cf3  mov     r8d, [rax+4]; unsigned int
0x180004cf7  lea     rdx, [rax+8]; unsigned __int16 *
0x180004cfb  call    ?PerflibciFindInstance@@YAPEAUPERFLIBCI_INSTANCE_NODE@@PEAUPERFLIBCI_COUNTERSET_NODE@@PEAGKKH@Z; PerflibciFindInstance(PERFLIBCI_COUNTERSET_NODE *,ushort *,ulong,ulong,int)
0x180004d00  mov     ebx, [rsp+98h+var_50]
0x180004d04  test    rax, rax
0x180004d07  mov     rax, [rsp+98h+Src]
0x180004d0c  jz      short loc_180004D59
0x180004d0e  inc     ebx
0x180004d10  test    byte ptr [r15+58h], 2
0x180004d15  mov     [rsp+98h+var_50], ebx
0x180004d19  jz      short loc_180004D59
0x180004d1b  test    r12, r12
0x180004d1e  jz      loc_180004E3A
0x180004d24  mov     edx, [rax]
0x180004d26  lea     ecx, [rdx+rbp]
0x180004d29  cmp     ebp, ecx
0x180004d2b  ja      loc_180004E3A
0x180004d31  cmp     edx, ecx
0x180004d33  ja      loc_180004E3A
0x180004d39  cmp     ecx, r13d
0x180004d3c  ja      loc_180004E3A
0x180004d42  mov     r8d, edx; Size
0x180004d45  mov     ecx, ebp
0x180004d47  add     rcx, r12; void *
0x180004d4a  mov     rdx, rax; Src
0x180004d4d  call    memcpy_0
0x180004d52  mov     rax, [rsp+98h+Src]
0x180004d57  add     ebp, [rax]
0x180004d59  mov     r9d, [rsp+98h+var_44]
0x180004d5e  add     r9d, [rax]
0x180004d61  mov     ecx, [rdi]
0x180004d63  mov     edx, r9d
0x180004d66  mov     [rsp+98h+var_44], r9d
0x180004d6b  lea     rax, [rcx-8]
0x180004d6f  cmp     rdx, rax
0x180004d72  jb      loc_180004CA0
0x180004d78  mov     edx, [rsp+98h+var_3C]
0x180004d7c  mov     r10d, [rsp+98h+var_30]
0x180004d81  mov     dword ptr [rsp+98h+Src], ebp
0x180004d85  mov     ebp, [rsp+98h+var_40]
0x180004d89  mov     rcx, [rsp+98h+hMem]
0x180004d8e  jmp     loc_180004C33
0x180004d93  test    ebx, ebx
0x180004d95  jz      loc_180004B71
0x180004d9b  inc     ebx
0x180004d9d  test    r12, r12
0x180004da0  jz      loc_180004E6F
0x180004da6  mov     edx, dword ptr [rsp+98h+Src]
0x180004daa  lea     r10d, [rdx+18h]
0x180004dae  cmp     edx, r10d
0x180004db1  jnb     loc_180004E73
0x180004db7  cmp     r10d, 18h
0x180004dbb  jb      loc_180004E73
0x180004dc1  cmp     r10d, r13d
0x180004dc4  ja      loc_180004E73
0x180004dca  mov     qword ptr [rdx+r12], 18h
0x180004dd2  lea     r9, String2; "_Total"
0x180004dd9  add     rdx, 8
0x180004ddd  mov     ecx, 7FFFFFFEh
0x180004de2  add     rdx, r12
0x180004de5  mov     r8d, 7
0x180004deb  nop     dword ptr [rax+rax+00h]
0x180004df0  test    rcx, rcx
0x180004df3  jz      short loc_180004E12
0x180004df5  movzx   eax, word ptr [r9]
0x180004df9  test    ax, ax
0x180004dfc  jz      short loc_180004E12
0x180004dfe  mov     [rdx], ax
0x180004e01  add     r9, 2
0x180004e05  add     rdx, 2
0x180004e09  dec     rcx
0x180004e0c  sub     r8, 1
0x180004e10  jnz     short loc_180004DF0
0x180004e12  test    r8, r8
0x180004e15  lea     rcx, [rdx-2]
0x180004e19  cmovnz  rcx, rdx
0x180004e1d  xor     eax, eax
0x180004e1f  mov     edx, r10d
0x180004e22  mov     [rcx], ax
0x180004e25  mov     rcx, [rsp+98h+hMem]
0x180004e2a  jmp     loc_180004B75
0x180004e2f  mov     r14d, 0Eh
0x180004e35  jmp     loc_180004AB1
0x180004e3a  mov     r14d, 8
0x180004e40  jmp     loc_180004D57
  ... truncated ...
```
