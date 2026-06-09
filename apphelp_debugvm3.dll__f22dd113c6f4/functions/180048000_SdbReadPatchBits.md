# SdbReadPatchBits

- ea: `0x180048000`
- end: `0x1800481ea`
- name: `SdbReadPatchBits`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x180006c20`
- `0x180009720`
- `0x18000ae70`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x180048000`
- `0x18004c3a0`
- `0x18004c404`
- `0x18004ec04`

## string_xrefs

- `0x180048041`: `SdbReadPatchBits`
- `0x18004807a`: `SdbReadPatchBits`
- `0x1800480ac`: `SdbReadPatchBits`
- `0x1800480f2`: `SdbReadPatchBits`
- `0x18004812a`: `SdbReadPatchBits`
- `0x18004815a`: `SdbReadPatchBits`
- `0x18004817f`: `SdbReadPatchBits`
- `0x1800481ba`: `SdbReadPatchBits`
- `0x18004809f`: `Can't read the name of the patch`

## pseudocode

```c
__int64 __fastcall SdbReadPatchBits(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  int v6; // r14d
  unsigned int v8; // ebx
  unsigned int FirstTag; // eax
  unsigned int ItemFromItemRef; // eax
  unsigned int FirstTagRef; // eax
  unsigned int v12; // r14d
  unsigned int TagRefDataSize; // eax
  bool v14; // cc
  _DWORD v16[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17[6]; // [rsp+38h] [rbp-30h] BYREF

  v6 = a2;
  v8 = 0;
  v16[0] = 0;
  v17[0] = 0;
  if ( (unsigned int)SdbTagRefToTagID(a1, a2, v17, v16) )
  {
    FirstTag = SdbFindFirstTag(v17[0], v16[0], 24577);
    if ( FirstTag )
    {
      if ( SdbGetStringTagPtr(v17[0], FirstTag) )
      {
        ItemFromItemRef = SdbGetItemFromItemRef(a1, v6, 24577, 16389, 28677);
        if ( ItemFromItemRef )
        {
          FirstTagRef = SdbFindFirstTagRef(a1, ItemFromItemRef, 36866);
          v12 = FirstTagRef;
          if ( FirstTagRef )
          {
            TagRefDataSize = SdbpGetTagRefDataSize(a1, FirstTagRef);
            if ( TagRefDataSize )
            {
              if ( TagRefDataSize == 0x20000000 )
              {
                AslLogCallPrintf(1, "SdbReadPatchBits", 2203, "Corrupt database: invalid sized patch");
              }
              else
              {
                v14 = TagRefDataSize <= *a4;
                *a4 = TagRefDataSize;
                if ( v14 )
                {
                  if ( (unsigned int)SdbpReadBinaryTagRef(a1, v12, a3, TagRefDataSize) )
                  {
                    v8 = 1;
                    v16[1] = 1;
                  }
                  else
                  {
                    AslLogCallPrintf(1, "SdbReadPatchBits", 2221, "Cannot get the patch bits");
                  }
                }
              }
            }
            else
            {
              AslLogCallPrintf(1, "SdbReadPatchBits", 2199, "Corrupt database: zero sized patch");
            }
          }
          else
          {
            AslLogCallPrintf(1, "SdbReadPatchBits", 2192, "Can't get the patch bits tag");
          }
        }
        else
        {
          AslLogCallPrintf(1, "SdbReadPatchBits", 2186, "Can't get the patch tag");
        }
      }
      else
      {
        AslLogCallPrintf(1, "SdbReadPatchBits", 2177, "Can't read the name of the patch");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbReadPatchBits", 2171, "Can't find the name tag");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbReadPatchBits", 2165, "Can't convert tag ref");
  }
  return v8;
}

```

## disassembly

```asm
0x180048000  mov     rax, rsp
0x180048003  push    rbx
0x180048004  push    rsi
0x180048005  push    rdi
0x180048006  push    r14
0x180048008  push    r15
0x18004800a  sub     rsp, 40h
0x18004800e  mov     rsi, r9
0x180048011  mov     r15, r8
0x180048014  mov     r14d, edx
0x180048017  mov     rdi, rcx
0x18004801a  xor     ebx, ebx
0x18004801c  mov     [rax-38h], ebx
0x18004801f  mov     [rax-30h], rbx
0x180048023  lea     r9, [rax-38h]
0x180048027  lea     r8, [rax-30h]
0x18004802b  call    SdbTagRefToTagID
0x180048030  test    eax, eax
0x180048032  jnz     short loc_180048055
0x180048034  lea     r9, aCanTConvertTag; "Can't convert tag ref"
0x18004803b  mov     r8d, 875h
0x180048041  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x180048048  lea     ecx, [rbx+1]
0x18004804b  call    AslLogCallPrintf
0x180048050  jmp     loc_1800481DC
0x180048055  mov     r8d, 6001h
0x18004805b  mov     edx, [rsp+68h+var_38]
0x18004805f  mov     rcx, [rsp+68h+var_30]
0x180048064  call    SdbFindFirstTag
0x180048069  test    eax, eax
0x18004806b  jnz     short loc_18004808E
0x18004806d  lea     r9, aCanTFindTheNam; "Can't find the name tag"
0x180048074  mov     r8d, 87Bh
0x18004807a  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x180048081  lea     ecx, [rax+1]
0x180048084  call    AslLogCallPrintf
0x180048089  jmp     loc_1800481DC
0x18004808e  mov     edx, eax
0x180048090  mov     rcx, [rsp+68h+var_30]
0x180048095  call    SdbGetStringTagPtr
0x18004809a  test    rax, rax
0x18004809d  jnz     short loc_1800480C0
0x18004809f  lea     r9, aCanTReadTheNam; "Can't read the name of the patch"
0x1800480a6  mov     r8d, 881h
0x1800480ac  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x1800480b3  lea     ecx, [rax+1]
0x1800480b6  call    AslLogCallPrintf
0x1800480bb  jmp     loc_1800481DC
0x1800480c0  mov     eax, 7005h
0x1800480c5  mov     r9d, 4005h
0x1800480cb  mov     r8d, 6001h
0x1800480d1  mov     [rsp+68h+var_48], ax
0x1800480d6  mov     edx, r14d
0x1800480d9  mov     rcx, rdi
0x1800480dc  call    SdbGetItemFromItemRef
0x1800480e1  test    eax, eax
0x1800480e3  jnz     short loc_180048106
0x1800480e5  lea     r9, aCanTGetThePatc_0; "Can't get the patch tag"
0x1800480ec  mov     r8d, 88Ah
0x1800480f2  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x1800480f9  lea     ecx, [rax+1]
0x1800480fc  call    AslLogCallPrintf
0x180048101  jmp     loc_1800481DC
0x180048106  mov     r8d, 9002h
0x18004810c  mov     edx, eax
0x18004810e  mov     rcx, rdi
0x180048111  call    SdbFindFirstTagRef
0x180048116  mov     r14d, eax
0x180048119  test    eax, eax
0x18004811b  jnz     short loc_18004813E
0x18004811d  lea     r9, aCanTGetThePatc; "Can't get the patch bits tag"
0x180048124  mov     r8d, 890h
0x18004812a  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x180048131  lea     ecx, [rax+1]
0x180048134  call    AslLogCallPrintf
0x180048139  jmp     loc_1800481DC
0x18004813e  mov     edx, r14d
0x180048141  mov     rcx, rdi
0x180048144  call    SdbpGetTagRefDataSize
0x180048149  test    eax, eax
0x18004814b  jnz     short loc_18004816B
0x18004814d  lea     r9, aCorruptDatabas_0; "Corrupt database: zero sized patch"
0x180048154  mov     r8d, 897h
0x18004815a  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x180048161  lea     ecx, [rax+1]
0x180048164  call    AslLogCallPrintf
0x180048169  jmp     short loc_1800481DC
0x18004816b  cmp     eax, 20000000h
0x180048170  jnz     short loc_180048192
0x180048172  lea     r9, aCorruptDatabas; "Corrupt database: invalid sized patch"
0x180048179  mov     r8d, 89Bh
0x18004817f  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x180048186  mov     ecx, 1
0x18004818b  call    AslLogCallPrintf
0x180048190  jmp     short loc_1800481DC
0x180048192  cmp     eax, [rsi]
0x180048194  mov     [rsi], eax
0x180048196  ja      short loc_1800481DC
0x180048198  mov     r9d, eax
0x18004819b  mov     r8, r15
0x18004819e  mov     edx, r14d
0x1800481a1  mov     rcx, rdi
0x1800481a4  call    SdbpReadBinaryTagRef
0x1800481a9  test    eax, eax
0x1800481ab  jnz     short loc_1800481CB
0x1800481ad  lea     r9, aCannotGetThePa; "Cannot get the patch bits"
0x1800481b4  mov     r8d, 8ADh
0x1800481ba  lea     rdx, aSdbreadpatchbi_0; "SdbReadPatchBits"
0x1800481c1  lea     ecx, [rax+1]
0x1800481c4  call    AslLogCallPrintf
0x1800481c9  jmp     short loc_1800481DC
0x1800481cb  mov     ebx, 1
0x1800481d0  mov     [rsp+68h+var_34], ebx
0x1800481d4  jmp     short loc_1800481DC
0x1800481d6  xor     ebx, ebx
0x1800481d8  mov     [rsp+68h+var_34], ebx
0x1800481dc  mov     eax, ebx
0x1800481de  add     rsp, 40h
0x1800481e2  pop     r15
0x1800481e4  pop     r14
0x1800481e6  pop     rdi
0x1800481e7  pop     rsi
0x1800481e8  pop     rbx
0x1800481e9  retn
0x180059520  push    rbp
0x180059522  sub     rsp, 30h
0x180059526  mov     rbp, rdx
0x180059529  call    ShimExceptionHandler
0x18005952e  nop
0x18005952f  add     rsp, 30h
0x180059533  pop     rbp
0x180059534  retn
```
