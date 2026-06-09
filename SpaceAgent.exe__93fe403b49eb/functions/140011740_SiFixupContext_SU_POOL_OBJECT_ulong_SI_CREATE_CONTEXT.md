# SiFixupContext(_SU_POOL_OBJECT *,ulong,_SI_CREATE_CONTEXT *)

- ea: `0x140011740`
- end: `0x140011908`
- name: `?SiFixupContext@@YAHPEAU_SU_POOL_OBJECT@@KPEAU_SI_CREATE_CONTEXT@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, unsigned int, struct _SI_CREATE_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010b5c`

## callees

- `0x14000fb68`
- `0x140011740`
- `0x140013c90`
- `0x140013e1c`
- `0x140013e84`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400118aa`
- `KERNEL32!SetLastError` at `0x1400118aa`

## pseudocode

```c
__int64 __fastcall SiFixupContext(struct _SU_POOL_OBJECT *a1, unsigned int a2, struct _SI_CREATE_CONTEXT *a3)
{
  unsigned int v3; // r15d
  struct _SI_CREATE_CONTEXT *v5; // r11
  unsigned int v6; // ebx
  struct _SU_POOL_OBJECT *v7; // r10
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebp
  unsigned int v11; // edi
  unsigned int v12; // r10d
  __int64 v13; // rsi
  __int64 v14; // r15
  SP_RESILIENCY_INFO *v15; // r13
  unsigned int v16; // eax
  unsigned int v17; // r10d
  unsigned int v18; // r12d
  unsigned int v19; // eax
  unsigned int v20; // r10d
  __int64 v21; // rdi
  __int64 v22; // rcx
  unsigned int v23; // r9d
  __int64 v24; // r10
  __int64 v25; // rdi
  unsigned int v26; // eax
  unsigned __int64 v27; // r8
  unsigned __int64 v29; // [rsp+60h] [rbp+8h]
  unsigned int v30; // [rsp+68h] [rbp+10h]

  v3 = 0;
  v5 = a3;
  v30 = 0;
  v6 = 1;
  v7 = a1;
  _BitScanReverse64(
    (unsigned __int64 *)&a1,
    ((*((_QWORD *)a1 + 334) << 6)
   + (unsigned int)((*((_DWORD *)a1 + 676) >> 1) - 1)
   - ((*((_QWORD *)a1 + 334) << 6) + (unsigned __int64)(unsigned int)((*((_DWORD *)a1 + 676) >> 1) - 1))
   % ((unsigned __int64)*((unsigned int *)a1 + 676) >> 1))
  / ((unsigned __int64)*((unsigned int *)a1 + 676) >> 1));
  v8 = 1LL << ((unsigned __int8)a1 + 1);
  v9 = *((_QWORD *)v7 + 342);
  if ( v8 > v9 )
    v9 = v8;
  v29 = v9;
  while ( 1 )
  {
    v10 = 0;
    v11 = 0;
    v12 = 1;
    if ( a2 )
    {
      v13 = 0;
      do
      {
        v14 = 56 * v13;
        if ( (*((_BYTE *)v5 + 56 * v13) & 1) != 0
          && ((v15 = *(SP_RESILIENCY_INFO **)((char *)v5 + v14 + 16),
               v16 = SP_RESILIENCY_INFO::NumberOfDataColumns(v15),
               v18 = v16,
               !v17)
           || !v16
            ? (v12 = 0)
            : (v19 = GreatestCommonDivisor(v17, v16), v12 = v18 * (v20 / v19)),
              *((_DWORD *)v15 + 4) - *(_DWORD *)((char *)v5 + v14 + 52) > v10) )
        {
          v10 = *((_DWORD *)v15 + 4) - *(_DWORD *)((char *)v5 + v14 + 52);
          v30 = v11;
          v3 = v11;
        }
        else
        {
          v3 = v30;
        }
        ++v11;
        ++v13;
      }
      while ( v11 < a2 );
    }
    if ( v29 * v12 <= 0x400000000LL )
      break;
    if ( !v10 )
    {
      SetLastError(0x13Au);
      return 0;
    }
    v21 = 56LL * v3;
    --*(_DWORD *)(*(_QWORD *)((char *)v5 + v21 + 16) + 16LL);
    if ( (*((_BYTE *)v5 + v21) & 2) != 0 )
      SP_RESILIENCY_INFO::SetNumberOfGroups(
        *(_QWORD *)((char *)v5 + v21 + 16),
        *(unsigned int *)(*(_QWORD *)((char *)v5 + v21 + 8) + 16LL));
    v22 = *(_QWORD *)((char *)v5 + v21 + 16);
    if ( *(_DWORD *)(v22 + 16) > *(_DWORD *)((char *)v5 + v21 + 52) )
      SP_RESILIENCY_INFO::SetNumberOfColumns(v22, *(unsigned int *)(*(_QWORD *)((char *)v5 + v21 + 8) + 16LL));
  }
  v23 = 0;
  if ( a2 )
  {
    v24 = 0;
    do
    {
      v25 = 56 * v24;
      if ( (*((_BYTE *)v5 + 56 * v24) & 1) != 0 )
      {
        v26 = SP_RESILIENCY_INFO::NumberOfDataColumns(*(SP_RESILIENCY_INFO **)((char *)v5 + v25 + 16));
        *(_QWORD *)(*(_QWORD *)((char *)v5 + v25 + 8) + 8LL) = v27 / v26;
      }
      ++v23;
      ++v24;
    }
    while ( v23 < a2 );
  }
  return v6;
}

```

## disassembly

```asm
0x140011740  mov     [rsp+arg_10], rbx
0x140011745  push    rbp
0x140011746  push    rsi
0x140011747  push    rdi
0x140011748  push    r12
0x14001174a  push    r13
0x14001174c  push    r14
0x14001174e  push    r15
0x140011750  sub     rsp, 20h
0x140011754  mov     eax, [rcx+0A90h]
0x14001175a  xor     r15d, r15d
0x14001175d  mov     r9d, eax
0x140011760  mov     [rsp+58h+arg_8], 0
0x140011768  shr     eax, 1
0x14001176a  mov     r14d, edx
0x14001176d  xor     edx, edx
0x14001176f  shr     r9, 1
0x140011772  mov     r11, r8
0x140011775  mov     [rsp+58h+arg_8], r15d
0x14001177a  lea     ebx, [r15+1]
0x14001177e  mov     r10, rcx
0x140011781  sub     eax, ebx
0x140011783  mov     r8d, eax
0x140011786  mov     rax, [rcx+0A70h]
0x14001178d  shl     rax, 6
0x140011791  add     r8, rax
0x140011794  mov     rax, r8
0x140011797  div     r9
0x14001179a  sub     r8, rdx
0x14001179d  xor     edx, edx
0x14001179f  mov     rax, r8
0x1400117a2  div     r9
0x1400117a5  bsr     rcx, rax
0x1400117a9  mov     eax, ebx
0x1400117ab  inc     ecx
0x1400117ad  shl     rax, cl
0x1400117b0  mov     rcx, [r10+0AB0h]
0x1400117b7  cmp     rax, rcx
0x1400117ba  cmova   rcx, rax
0x1400117be  mov     [rsp+58h+arg_0], rcx
0x1400117c3  xor     ebp, ebp
0x1400117c5  xor     edi, edi
0x1400117c7  mov     r10d, ebx
0x1400117ca  test    r14d, r14d
0x1400117cd  jz      short loc_14001183C
0x1400117cf  xor     esi, esi
0x1400117d1  imul    r15, rsi, 38h ; '8'
0x1400117d5  test    [r15+r11], bl
0x1400117d9  jz      short loc_14001182D
0x1400117db  mov     r13, [r15+r11+10h]
0x1400117e0  mov     rcx, r13; this
0x1400117e3  call    ?NumberOfDataColumns@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfDataColumns(void)
0x1400117e8  mov     r12d, eax
0x1400117eb  test    r10d, r10d
0x1400117ee  jz      short loc_140011812
0x1400117f0  test    eax, eax
0x1400117f2  jz      short loc_140011812
0x1400117f4  mov     edx, eax; unsigned int
0x1400117f6  mov     ecx, r10d; unsigned int
0x1400117f9  call    ?GreatestCommonDivisor@@YAKKK@Z; GreatestCommonDivisor(ulong,ulong)
0x1400117fe  mov     r9d, eax
0x140011801  xor     edx, edx
0x140011803  mov     eax, r10d
0x140011806  div     r9d
0x140011809  mov     r10d, eax
0x14001180c  imul    r10d, r12d
0x140011810  jmp     short loc_140011815
0x140011812  xor     r10d, r10d
0x140011815  mov     eax, [r13+10h]
0x140011819  sub     eax, [r15+r11+34h]
0x14001181e  cmp     eax, ebp
0x140011820  jbe     short loc_14001182D
0x140011822  mov     ebp, eax
0x140011824  mov     [rsp+58h+arg_8], edi
0x140011828  mov     r15d, edi
0x14001182b  jmp     short loc_140011832
0x14001182d  mov     r15d, [rsp+58h+arg_8]
0x140011832  add     edi, ebx
0x140011834  add     rsi, rbx
0x140011837  cmp     edi, r14d
0x14001183a  jb      short loc_1400117D1
0x14001183c  mov     r8d, r10d
0x14001183f  mov     rax, 400000000h
0x140011849  imul    r8, [rsp+58h+arg_0]
0x14001184f  cmp     r8, rax
0x140011852  jbe     short loc_1400118B4
0x140011854  test    ebp, ebp
0x140011856  jz      short loc_1400118A5
0x140011858  mov     eax, r15d
0x14001185b  imul    rdi, rax, 38h ; '8'
0x14001185f  mov     rax, [rdi+r11+10h]
0x140011864  dec     dword ptr [rax+10h]
0x140011867  test    byte ptr [rdi+r11], 2
0x14001186c  jz      short loc_140011880
0x14001186e  mov     rdx, [rdi+r11+8]
0x140011873  mov     rcx, [rdi+r11+10h]
0x140011878  mov     edx, [rdx+10h]
0x14001187b  call    ?SetNumberOfGroups@SP_RESILIENCY_INFO@@QEAAXW4_SC_MEDIA_TYPE@@@Z; SP_RESILIENCY_INFO::SetNumberOfGroups(_SC_MEDIA_TYPE)
0x140011880  mov     rcx, [rdi+r11+10h]
0x140011885  mov     eax, [rdi+r11+34h]
0x14001188a  cmp     [rcx+10h], eax
0x14001188d  jbe     loc_1400117C3
0x140011893  mov     rdx, [rdi+r11+8]
0x140011898  mov     edx, [rdx+10h]
0x14001189b  call    ?SetNumberOfColumns@SP_RESILIENCY_INFO@@QEAAXW4_SC_MEDIA_TYPE@@@Z; SP_RESILIENCY_INFO::SetNumberOfColumns(_SC_MEDIA_TYPE)
0x1400118a0  jmp     loc_1400117C3
0x1400118a5  mov     ecx, 13Ah; dwErrCode
0x1400118aa  call    cs:__imp_SetLastError
0x1400118b0  xor     ebx, ebx
0x1400118b2  jmp     short loc_1400118F1
0x1400118b4  xor     r9d, r9d
0x1400118b7  test    r14d, r14d
0x1400118ba  jz      short loc_1400118F1
0x1400118bc  xor     r10d, r10d
0x1400118bf  imul    rdi, r10, 38h ; '8'
0x1400118c3  test    [rdi+r11], bl
0x1400118c7  jz      short loc_1400118E6
0x1400118c9  mov     rcx, [rdi+r11+10h]; this
0x1400118ce  call    ?NumberOfDataColumns@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfDataColumns(void)
0x1400118d3  mov     ecx, eax
0x1400118d5  xor     edx, edx
0x1400118d7  mov     rax, r8
0x1400118da  div     rcx
0x1400118dd  mov     rcx, [rdi+r11+8]
0x1400118e2  mov     [rcx+8], rax
0x1400118e6  add     r9d, ebx
0x1400118e9  add     r10, rbx
0x1400118ec  cmp     r9d, r14d
0x1400118ef  jb      short loc_1400118BF
0x1400118f1  mov     eax, ebx
0x1400118f3  mov     rbx, [rsp+58h+arg_10]
0x1400118f8  add     rsp, 20h
0x1400118fc  pop     r15
0x1400118fe  pop     r14
0x140011900  pop     r13
0x140011902  pop     r12
0x140011904  pop     rdi
0x140011905  pop     rsi
0x140011906  pop     rbp
0x140011907  retn
```
