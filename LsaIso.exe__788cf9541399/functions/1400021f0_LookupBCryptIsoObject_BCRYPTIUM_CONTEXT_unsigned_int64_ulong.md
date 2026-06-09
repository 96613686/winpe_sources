# LookupBCryptIsoObject(BCRYPTIUM_CONTEXT *,unsigned __int64,ulong)

- ea: `0x1400021f0`
- end: `0x14000237b`
- name: `?LookupBCryptIsoObject@@YAPEAU_BCRYPT_ISO_OBJECT@@PEAUBCRYPTIUM_CONTEXT@@_KK@Z`
- size: `395`
- prototype: `struct _BCRYPT_ISO_OBJECT *__fastcall(struct BCRYPTIUM_CONTEXT *, unsigned __int64, unsigned int)`
- caller_count: `21`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140002390`
- `0x140002620`
- `0x140008538`
- `0x14000e370`
- `0x14000e510`
- `0x14000e830`
- `0x14000ea40`
- `0x14000ec10`
- `0x14000ed50`
- `0x14000ee90`
- `0x14000f0d0`
- `0x14000f300`
- `0x14000f520`
- `0x14000fc50`
- `0x14000fe40`
- `0x1400100d0`
- `0x1400106a0`
- `0x140010b50`
- `0x1400110a0`
- `0x1400113a0`
- `0x140011730`

## callees

- `0x140002160`
- `0x1400021f0`
- `0x14001193c`
- `0x1400119f8`
- `0x140011ad0`
- `0x140011b30`
- `0x140011b74`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x14000233e`
- `ntdll!RtlLeaveCriticalSection` at `0x14000233e`
- `ntdll!RtlEnterCriticalSection` at `0x14000223e`
- `ntdll!RtlEnterCriticalSection` at `0x14000223e`

## pseudocode

```c
struct _BCRYPT_ISO_OBJECT *__fastcall LookupBCryptIsoObject(
        struct BCRYPTIUM_CONTEXT *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  int v3; // ebp
  struct _BCRYPT_ISO_OBJECT *v6; // rdi
  struct _RTL_CRITICAL_SECTION *v7; // r14
  __int64 v8; // r8
  __int64 v9; // rax
  unsigned int *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8

  v3 = a3;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, a3, a2, a3);
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 24);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 24));
  if ( a2 && a2 < *((unsigned int *)a1 + 16) )
  {
    _mm_lfence();
    v9 = *((_QWORD *)a1 + 9);
    v10 = *(unsigned int **)(v9 + 8 * a2);
    if ( ((unsigned __int8)v10 & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v8, a2);
    }
    else if ( v10[1] == 1112100685 && (!v3 || v10[5] == v3) )
    {
      v6 = *(struct _BCRYPT_ISO_OBJECT **)(v9 + 8 * a2);
      BCryptIumReferenceObject(v6);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_DLd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v10[1], v10[5], v10[8]);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DDLL(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v8, a2, *((_DWORD *)a1 + 16));
  }
  RtlLeaveCriticalSection(v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x1400021f0  push    rbx
0x1400021f2  push    rbp
0x1400021f3  push    rsi
0x1400021f4  push    rdi
0x1400021f5  push    r14
0x1400021f7  push    r15
0x1400021f9  sub     rsp, 48h
0x1400021fd  mov     ebp, r8d
0x140002200  mov     rsi, rdx
0x140002203  mov     rbx, rcx
0x140002206  xor     edi, edi
0x140002208  mov     rcx, cs:WPP_GLOBAL_Control
0x14000220f  lea     r15, WPP_GLOBAL_Control
0x140002216  cmp     rcx, r15
0x140002219  jz      short loc_140002237
0x14000221b  test    byte ptr [rcx+1Ch], 4
0x14000221f  jz      short loc_140002237
0x140002221  mov     rcx, [rcx+10h]
0x140002225  mov     edx, 2Bh ; '+'
0x14000222a  mov     r9, rsi
0x14000222d  mov     [rsp+78h+var_58], r8d
0x140002232  call    WPP_SF_ID
0x140002237  lea     r14, [rbx+18h]
0x14000223b  mov     rcx, r14; CriticalSection
0x14000223e  call    cs:__imp_RtlEnterCriticalSection
0x140002244  test    rsi, rsi
0x140002247  jz      loc_140002311
0x14000224d  mov     eax, [rbx+40h]
0x140002250  cmp     rsi, rax
0x140002253  jnb     loc_140002311
0x140002259  lfence
0x14000225c  mov     rax, [rbx+48h]
0x140002260  mov     rbx, [rax+rsi*8]
0x140002264  test    bl, 1
0x140002267  jz      short loc_140002299
0x140002269  mov     rcx, cs:WPP_GLOBAL_Control
0x140002270  cmp     rcx, r15
0x140002273  jz      loc_14000233B
0x140002279  test    byte ptr [rcx+1Ch], 1
0x14000227d  jz      loc_14000233B
0x140002283  mov     rcx, [rcx+10h]
0x140002287  mov     edx, 2Eh ; '.'
0x14000228c  mov     r9, rsi
0x14000228f  call    WPP_SF_I
0x140002294  jmp     loc_14000233B
0x140002299  mov     r9d, [rbx+4]
0x14000229d  cmp     r9d, 42494F4Dh
0x1400022a4  jnz     short loc_1400022E9
0x1400022a6  test    ebp, ebp
0x1400022a8  jz      short loc_1400022AF
0x1400022aa  cmp     [rbx+14h], ebp
0x1400022ad  jnz     short loc_1400022E9
0x1400022af  mov     rcx, rbx; struct _BCRYPT_ISO_OBJECT *
0x1400022b2  mov     rdi, rbx
0x1400022b5  call    ?BCryptIumReferenceObject@@YAJPEAU_BCRYPT_ISO_OBJECT@@@Z; BCryptIumReferenceObject(_BCRYPT_ISO_OBJECT *)
0x1400022ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022c1  cmp     rcx, r15
0x1400022c4  jz      short loc_14000233B
0x1400022c6  test    byte ptr [rcx+1Ch], 4
0x1400022ca  jz      short loc_14000233B
0x1400022cc  mov     eax, [rbx+20h]
0x1400022cf  mov     r9d, [rbx+4]
0x1400022d3  mov     rcx, [rcx+10h]
0x1400022d7  mov     [rsp+78h+var_50], eax
0x1400022db  mov     eax, [rbx+14h]
0x1400022de  mov     [rsp+78h+var_58], eax
0x1400022e2  call    WPP_SF_DLd
0x1400022e7  jmp     short loc_14000233B
0x1400022e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022f0  cmp     rcx, r15
0x1400022f3  jz      short loc_14000233B
0x1400022f5  test    byte ptr [rcx+1Ch], 1
0x1400022f9  jz      short loc_14000233B
0x1400022fb  mov     eax, [rbx+14h]
0x1400022fe  mov     rcx, [rcx+10h]
0x140002302  mov     [rsp+78h+var_48], ebp
0x140002306  mov     [rsp+78h+var_50], eax
0x14000230a  call    WPP_SF_DDLL
0x14000230f  jmp     short loc_14000233B
0x140002311  mov     rcx, cs:WPP_GLOBAL_Control
0x140002318  cmp     rcx, r15
0x14000231b  jz      short loc_14000233B
0x14000231d  test    byte ptr [rcx+1Ch], 1
0x140002321  jz      short loc_14000233B
0x140002323  mov     eax, [rbx+40h]
0x140002326  mov     edx, 2Dh ; '-'
0x14000232b  mov     rcx, [rcx+10h]
0x14000232f  mov     r9, rsi
0x140002332  mov     [rsp+78h+var_58], eax
0x140002336  call    WPP_SF_ID
0x14000233b  mov     rcx, r14; CriticalSection
0x14000233e  call    cs:__imp_RtlLeaveCriticalSection
0x140002344  mov     rcx, cs:WPP_GLOBAL_Control
0x14000234b  cmp     rcx, r15
0x14000234e  jz      short loc_14000236B
0x140002350  test    byte ptr [rcx+1Ch], 4
0x140002354  jz      short loc_14000236B
0x140002356  mov     rcx, [rcx+10h]
0x14000235a  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids
0x140002361  mov     edx, 32h ; '2'
0x140002366  call    WPP_SF_
0x14000236b  mov     rax, rdi
0x14000236e  add     rsp, 48h
0x140002372  pop     r15
0x140002374  pop     r14
0x140002376  pop     rdi
0x140002377  pop     rsi
0x140002378  pop     rbp
0x140002379  pop     rbx
0x14000237a  retn
```
