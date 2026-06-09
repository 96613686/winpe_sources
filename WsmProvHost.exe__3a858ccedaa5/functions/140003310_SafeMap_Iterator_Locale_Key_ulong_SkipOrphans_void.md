# SafeMap_Iterator<Locale::Key,ulong>::SkipOrphans(void)

- ea: `0x140003310`
- end: `0x1400033b0`
- name: `?SkipOrphans@?$SafeMap_Iterator@VKey@Locale@@K@@IEAAXXZ`
- size: `160`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002960`
- `0x1400032b0`

## callees

- `0x140003310`

## import_xrefs

- `WsmSvc!WSManError` at `0x14000333e`
- `WsmSvc!WSManError` at `0x14000333e`

## pseudocode

```c
void __fastcall SafeMap_Iterator<Locale::Key,unsigned long>::SkipOrphans(_QWORD *a1)
{
  __int64 *v2; // r8
  __int64 v3; // rdx
  __int64 **v4; // rcx
  __int64 *j; // rdx
  __int64 i; // rax

  if ( a1[2] )
  {
    while ( 1 )
    {
      v2 = (__int64 *)a1[2];
      v3 = *v2;
      if ( *v2 == **(_QWORD **)(*a1 + 8LL) || !*(_BYTE *)(v3 + 68) )
        break;
      if ( !*(_BYTE *)(v3 + 25) )
      {
        v4 = *(__int64 ***)(v3 + 16);
        if ( *((_BYTE *)v4 + 25) )
        {
          for ( i = *(_QWORD *)(v3 + 8); !*(_BYTE *)(i + 25) && v3 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          {
            v3 = i;
            *v2 = i;
          }
          *v2 = i;
        }
        else
        {
          for ( j = *v4; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v4 = (__int64 **)j;
          *v2 = (__int64)v4;
        }
      }
    }
  }
  else
  {
    WSManError(L"onecore\\admin\\wmi\\wmx\\stdlib\\SafeMap.h", 0x1FDu, L"509", 0x54Fu, 0);
  }
}

```

## disassembly

```asm
0x140003310  sub     rsp, 38h
0x140003314  xor     r10d, r10d
0x140003317  mov     r9, rcx
0x14000331a  cmp     [rcx+10h], r10
0x14000331e  jnz     short loc_140003349
0x140003320  mov     r9d, 54Fh
0x140003326  mov     [rsp+38h+var_18], r10
0x14000332b  lea     r8, a509; "509"
0x140003332  mov     edx, 1FDh
0x140003337  lea     rcx, aOnecoreAdminWm; "onecore\\admin\\wmi\\wmx\\stdlib\\SafeM"...
0x14000333e  call    cs:__imp_?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x140003344  add     rsp, 38h
0x140003348  retn
0x140003349  mov     rax, [r9]
0x14000334c  mov     r8, [r9+10h]
0x140003350  mov     rcx, [rax+8]
0x140003354  mov     rdx, [r8]
0x140003357  cmp     rdx, [rcx]
0x14000335a  jz      short loc_140003344
0x14000335c  cmp     [rdx+44h], r10b
0x140003360  jz      short loc_140003344
0x140003362  cmp     [rdx+19h], r10b
0x140003366  jnz     short loc_140003349
0x140003368  mov     rcx, [rdx+10h]
0x14000336c  cmp     [rcx+19h], r10b
0x140003370  jnz     short loc_14000338F
0x140003372  mov     rdx, [rcx]
0x140003375  cmp     [rdx+19h], r10b
0x140003379  jnz     short loc_14000338A
0x14000337b  mov     rax, [rdx]
0x14000337e  mov     rcx, rdx
0x140003381  mov     rdx, rax
0x140003384  cmp     [rax+19h], r10b
0x140003388  jz      short loc_14000337B
0x14000338a  mov     [r8], rcx
0x14000338d  jmp     short loc_140003349
0x14000338f  mov     rax, [rdx+8]
0x140003393  jmp     short loc_1400033A5
0x140003395  cmp     rdx, [rax+10h]
0x140003399  jnz     short loc_1400033AB
0x14000339b  mov     rdx, rax
0x14000339e  mov     [r8], rax
0x1400033a1  mov     rax, [rax+8]
0x1400033a5  cmp     [rax+19h], r10b
0x1400033a9  jz      short loc_140003395
0x1400033ab  mov     [r8], rax
0x1400033ae  jmp     short loc_140003349
```
