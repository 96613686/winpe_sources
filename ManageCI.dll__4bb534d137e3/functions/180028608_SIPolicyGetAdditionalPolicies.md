# SIPolicyGetAdditionalPolicies

- ea: `0x180028608`
- end: `0x180028791`
- name: `SIPolicyGetAdditionalPolicies`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020f78`

## callees

- `0x180022e3c`
- `0x180028608`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002875e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002875e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800286b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800286b8`
- `bcd!BcdOpenObject` at `0x18002865d`
- `bcd!BcdOpenObject` at `0x18002865d`
- `bcd!BcdCloseStore` at `0x18002877c`
- `bcd!BcdCloseStore` at `0x18002877c`
- `bcd!BcdOpenStore` at `0x18002863e`
- `bcd!BcdOpenStore` at `0x18002863e`
- `bcd!BcdCloseObject` at `0x18002876d`
- `bcd!BcdCloseObject` at `0x18002876d`
- `bcd!BcdGetElementData` at `0x180028680`
- `bcd!BcdGetElementData` at `0x1800286e0`
- `bcd!BcdGetElementData` at `0x180028680`
- `bcd!BcdGetElementData` at `0x1800286e0`

## pseudocode

```c
__int64 __fastcall SIPolicyGetAdditionalPolicies(__int64 a1, unsigned int a2, unsigned int *a3)
{
  void *v6; // rdi
  int v7; // ebx
  int ElementData; // eax
  HLOCAL v9; // rax
  unsigned int v10; // edx
  __int64 i; // r8
  __int64 v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h] BYREF
  __int64 v16[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v17; // [rsp+98h] [rbp+50h] BYREF

  v15 = 0;
  v17 = 0;
  v6 = 0;
  v16[0] = 0;
  v7 = BcdOpenStore(0, 0, v16);
  if ( v7 >= 0 )
  {
    v7 = BcdOpenObject(v16[0], &GUID_WINDOWS_BOOTMGR, &v15);
    if ( v7 >= 0 )
    {
      v14 = 0;
      ElementData = BcdGetElementData(v15, 301990024, 0, &v14);
      v7 = ElementData;
      if ( ElementData == -1073741275 || !ElementData && v14 < 6 )
      {
        *a3 = 0;
        v7 = 0;
      }
      else if ( ElementData == -1073741789 )
      {
        v9 = LocalAlloc(0x40u, v14 + 2LL);
        v6 = v9;
        if ( v9 )
        {
          v7 = BcdGetElementData(v15, 301990024, v9, &v14);
          if ( v7 >= 0 )
          {
            v7 = SIPolicyParseAddtionalCiPolicyString(v6, 0, &v17);
            if ( v7 >= 0 )
            {
              if ( a1 )
              {
                if ( v17 <= a2 )
                {
                  v7 = SIPolicyParseAddtionalCiPolicyString(v6, a1, &v17);
                  if ( v7 >= 0 )
                  {
                    v10 = v17;
                    for ( i = 0; (unsigned int)i < v10; *(_BYTE *)(a1 + 8 * v12 + 18) = 1 )
                    {
                      v12 = 3 * i;
                      i = (unsigned int)(i + 1);
                      *(_WORD *)(a1 + 8 * v12 + 16) = 0;
                    }
                    *a3 = v10;
                  }
                }
                else
                {
                  v7 = -1073741789;
                }
              }
              else
              {
                *a3 = v17;
              }
            }
          }
        }
        else
        {
          v7 = -1073741801;
        }
      }
    }
  }
  LocalFree(v6);
  if ( v15 )
    BcdCloseObject();
  if ( v16[0] )
    BcdCloseStore();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028608  push    rbp
0x18002860a  push    rbx
0x18002860b  push    rsi
0x18002860c  push    rdi
0x18002860d  push    r14
0x18002860f  push    r15
0x180028611  mov     rbp, rsp
0x180028614  sub     rsp, 48h
0x180028618  mov     r14, r8
0x18002861b  mov     [rbp+var_20], 0
0x180028623  mov     r15d, edx
0x180028626  mov     [rbp+arg_18], 0
0x18002862d  mov     rsi, rcx
0x180028630  lea     r8, [rbp+var_18]
0x180028634  xor     edi, edi
0x180028636  xor     edx, edx
0x180028638  xor     ecx, ecx
0x18002863a  mov     [rbp+var_18], rdi
0x18002863e  call    cs:__imp_BcdOpenStore
0x180028644  mov     ebx, eax
0x180028646  test    eax, eax
0x180028648  js      loc_18002875B
0x18002864e  mov     rcx, [rbp+var_18]
0x180028652  lea     r8, [rbp+var_20]
0x180028656  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18002865d  call    cs:__imp_BcdOpenObject
0x180028663  mov     ebx, eax
0x180028665  test    eax, eax
0x180028667  js      loc_18002875B
0x18002866d  mov     rcx, [rbp+var_20]
0x180028671  lea     r9, [rbp+var_28]
0x180028675  xor     r8d, r8d
0x180028678  mov     [rbp+var_28], edi
0x18002867b  mov     edx, 12000088h
0x180028680  call    cs:__imp_BcdGetElementData
0x180028686  mov     ebx, eax
0x180028688  cmp     eax, 0C0000225h
0x18002868d  jz      loc_180028756
0x180028693  test    eax, eax
0x180028695  jnz     short loc_1800286A1
0x180028697  cmp     [rbp+var_28], 6
0x18002869b  jb      loc_180028756
0x1800286a1  cmp     eax, 0C0000023h
0x1800286a6  jnz     loc_18002875B
0x1800286ac  mov     edx, [rbp+var_28]
0x1800286af  mov     ecx, 40h ; '@'; uFlags
0x1800286b4  add     rdx, 2; uBytes
0x1800286b8  call    cs:__imp_LocalAlloc
0x1800286be  mov     rdi, rax
0x1800286c1  test    rax, rax
0x1800286c4  jnz     short loc_1800286D0
0x1800286c6  mov     ebx, 0C0000017h
0x1800286cb  jmp     loc_18002875B
0x1800286d0  mov     rcx, [rbp+var_20]
0x1800286d4  lea     r9, [rbp+var_28]
0x1800286d8  mov     r8, rdi
0x1800286db  mov     edx, 12000088h
0x1800286e0  call    cs:__imp_BcdGetElementData
0x1800286e6  mov     ebx, eax
0x1800286e8  test    eax, eax
0x1800286ea  js      short loc_18002875B
0x1800286ec  lea     r8, [rbp+arg_18]
0x1800286f0  xor     edx, edx
0x1800286f2  mov     rcx, rdi
0x1800286f5  call    SIPolicyParseAddtionalCiPolicyString
0x1800286fa  mov     ebx, eax
0x1800286fc  test    eax, eax
0x1800286fe  js      short loc_18002875B
0x180028700  test    rsi, rsi
0x180028703  jnz     short loc_18002870D
0x180028705  mov     eax, [rbp+arg_18]
0x180028708  mov     [r14], eax
0x18002870b  jmp     short loc_18002875B
0x18002870d  cmp     [rbp+arg_18], r15d
0x180028711  jbe     short loc_18002871A
0x180028713  mov     ebx, 0C0000023h
0x180028718  jmp     short loc_18002875B
0x18002871a  lea     r8, [rbp+arg_18]
0x18002871e  mov     rdx, rsi
0x180028721  mov     rcx, rdi
0x180028724  call    SIPolicyParseAddtionalCiPolicyString
0x180028729  mov     ebx, eax
0x18002872b  test    eax, eax
0x18002872d  js      short loc_18002875B
0x18002872f  mov     edx, [rbp+arg_18]
0x180028732  xor     r8d, r8d
0x180028735  test    edx, edx
0x180028737  jz      short loc_180028751
0x180028739  lea     rcx, [r8+r8*2]
0x18002873d  inc     r8d
0x180028740  mov     word ptr [rsi+rcx*8+10h], 0
0x180028747  mov     byte ptr [rsi+rcx*8+12h], 1
0x18002874c  cmp     r8d, edx
0x18002874f  jb      short loc_180028739
0x180028751  mov     [r14], edx
0x180028754  jmp     short loc_18002875B
0x180028756  mov     [r14], edi
0x180028759  xor     ebx, ebx
0x18002875b  mov     rcx, rdi; hMem
0x18002875e  call    cs:__imp_LocalFree
0x180028764  mov     rcx, [rbp+var_20]
0x180028768  test    rcx, rcx
0x18002876b  jz      short loc_180028773
0x18002876d  call    cs:__imp_BcdCloseObject
0x180028773  mov     rcx, [rbp+var_18]
0x180028777  test    rcx, rcx
0x18002877a  jz      short loc_180028782
0x18002877c  call    cs:__imp_BcdCloseStore
0x180028782  mov     eax, ebx
0x180028784  add     rsp, 48h
0x180028788  pop     r15
0x18002878a  pop     r14
0x18002878c  pop     rdi
0x18002878d  pop     rsi
0x18002878e  pop     rbx
0x18002878f  pop     rbp
0x180028790  retn
```
