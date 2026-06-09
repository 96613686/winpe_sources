# BfspCleanupDebuggerSettings

- ea: `0x18004df58`
- end: `0x18004e306`
- name: `BfspCleanupDebuggerSettings`
- size: `942`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18004d7e4`

## callees

- `0x18004cdd4`
- `0x18004df58`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18004e2b2`
- `bcd!BcdCloseObject` at `0x18004e2b2`
- `bcd!BcdOpenObject` at `0x18004dfa8`
- `bcd!BcdOpenObject` at `0x18004dfa8`
- `bcd!BcdGetElementData` at `0x18004dfdf`
- `bcd!BcdGetElementData` at `0x18004dfdf`
- `bcd!BcdDeleteElement` at `0x18004dfc1`
- `bcd!BcdDeleteElement` at `0x18004e025`
- `bcd!BcdDeleteElement` at `0x18004e049`
- `bcd!BcdDeleteElement` at `0x18004e068`
- `bcd!BcdDeleteElement` at `0x18004e087`
- `bcd!BcdDeleteElement` at `0x18004e0a6`
- `bcd!BcdDeleteElement` at `0x18004e0c5`
- `bcd!BcdDeleteElement` at `0x18004e0e4`
- `bcd!BcdDeleteElement` at `0x18004e103`
- `bcd!BcdDeleteElement` at `0x18004e122`
- `bcd!BcdDeleteElement` at `0x18004e140`
- `bcd!BcdDeleteElement` at `0x18004e164`
- `bcd!BcdDeleteElement` at `0x18004e183`
- `bcd!BcdDeleteElement` at `0x18004e1a1`
- `bcd!BcdDeleteElement` at `0x18004e1c5`
- `bcd!BcdDeleteElement` at `0x18004e1e0`
- `bcd!BcdDeleteElement` at `0x18004e204`
- `bcd!BcdDeleteElement` at `0x18004e223`
- `bcd!BcdDeleteElement` at `0x18004e242`
- `bcd!BcdDeleteElement` at `0x18004e261`
- `bcd!BcdDeleteElement` at `0x18004e27c`
- `bcd!BcdDeleteElement` at `0x18004e297`
- `bcd!BcdDeleteElement` at `0x18004e2ce`
- `bcd!BcdDeleteElement` at `0x18004dfc1`
- `bcd!BcdDeleteElement` at `0x18004e025`
- `bcd!BcdDeleteElement` at `0x18004e049`
- `bcd!BcdDeleteElement` at `0x18004e068`
- `bcd!BcdDeleteElement` at `0x18004e087`
- `bcd!BcdDeleteElement` at `0x18004e0a6`
- `bcd!BcdDeleteElement` at `0x18004e0c5`
- `bcd!BcdDeleteElement` at `0x18004e0e4`
- `bcd!BcdDeleteElement` at `0x18004e103`
- `bcd!BcdDeleteElement` at `0x18004e122`
- `bcd!BcdDeleteElement` at `0x18004e140`
- `bcd!BcdDeleteElement` at `0x18004e164`
- `bcd!BcdDeleteElement` at `0x18004e183`
- `bcd!BcdDeleteElement` at `0x18004e1a1`
- `bcd!BcdDeleteElement` at `0x18004e1c5`
- `bcd!BcdDeleteElement` at `0x18004e1e0`
- `bcd!BcdDeleteElement` at `0x18004e204`
- `bcd!BcdDeleteElement` at `0x18004e223`
- `bcd!BcdDeleteElement` at `0x18004e242`
- `bcd!BcdDeleteElement` at `0x18004e261`
- `bcd!BcdDeleteElement` at `0x18004e27c`
- `bcd!BcdDeleteElement` at `0x18004e297`
- `bcd!BcdDeleteElement` at `0x18004e2ce`

## string_xrefs

- `0x18004e2f0`: `Failed to delete debugger settings element %08x. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCleanupDebuggerSettings(__int64 a1)
{
  int ElementData; // edi
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  bool v12; // zf
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v26; // eax
  int v27; // [rsp+48h] [rbp+28h] BYREF
  __int64 v28; // [rsp+50h] [rbp+30h] BYREF
  __int64 v29; // [rsp+58h] [rbp+38h] BYREF

  v27 = 0;
  v28 = 0;
  v29 = 0;
  BfspLogMessage(2, L"Cleaning up debugger settings.");
  v28 = 0;
  ElementData = BcdOpenObject(a1, &GUID_DEBUGGER_SETTINGS_GROUP, &v28);
  if ( ElementData >= 0 )
  {
    BcdDeleteElement(v28, 369098763);
    v27 = 8;
    ElementData = BcdGetElementData(v28, 352321553, &v29, &v27);
    if ( ElementData >= 0 )
    {
      if ( v29 )
      {
        v3 = 352321555;
        if ( v29 != 1 )
        {
          if ( v29 != 2 )
          {
            if ( v29 != 3 )
            {
              v4 = BcdDeleteElement(v28, 352321555);
              ElementData = v4;
              if ( v4 >= 0 || v4 == -1073741275 )
              {
                v3 = 352321556;
                v5 = BcdDeleteElement(v28, 352321556);
                ElementData = v5;
                if ( v5 >= 0 || v5 == -1073741275 )
                {
                  v3 = 301989910;
                  v6 = BcdDeleteElement(v28, 301989910);
                  ElementData = v6;
                  if ( v6 >= 0 || v6 == -1073741275 )
                  {
                    v3 = 352321557;
                    v7 = BcdDeleteElement(v28, 352321557);
                    ElementData = v7;
                    if ( v7 >= 0 || v7 == -1073741275 )
                    {
                      v3 = 352321562;
                      v8 = BcdDeleteElement(v28, 352321562);
                      ElementData = v8;
                      if ( v8 >= 0 || v8 == -1073741275 )
                      {
                        v3 = 352321563;
                        v9 = BcdDeleteElement(v28, 352321563);
                        ElementData = v9;
                        if ( v9 >= 0 || v9 == -1073741275 )
                        {
                          v3 = 369098780;
                          v10 = BcdDeleteElement(v28, 369098780);
                          ElementData = v10;
                          if ( v10 >= 0 || v10 == -1073741275 )
                          {
                            v3 = 301989917;
                            v11 = BcdDeleteElement(v28, 301989917);
                            ElementData = v11;
                            if ( v11 >= 0 || v11 == -1073741275 )
                            {
                              v3 = 301989913;
                              ElementData = BcdDeleteElement(v28, 301989913);
                              if ( (int)(ElementData + 0x80000000) >= 0 )
                              {
                                v12 = ElementData == -1073741275;
                                goto LABEL_54;
                              }
                              goto LABEL_55;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
LABEL_62:
              BfspLogMessage(
                4,
                L"Failed to delete debugger settings element %08x. Status = [%x]",
                v3,
                (unsigned int)ElementData);
              goto LABEL_56;
            }
            v13 = BcdDeleteElement(v28, 352321555);
            ElementData = v13;
            if ( v13 < 0 && v13 != -1073741275 )
              goto LABEL_62;
            v3 = 352321556;
            v14 = BcdDeleteElement(v28, 352321556);
            ElementData = v14;
            if ( v14 < 0 && v14 != -1073741275 )
              goto LABEL_62;
            v3 = 352321557;
            v15 = BcdDeleteElement(v28, 352321557);
            ElementData = v15;
            if ( v15 < 0 && v15 != -1073741275 )
              goto LABEL_62;
            v3 = 301989910;
LABEL_52:
            v24 = BcdDeleteElement(v28, v3);
            ElementData = v24;
            if ( v24 < 0 )
            {
              v12 = v24 == -1073741275;
LABEL_54:
              if ( v12 )
                goto LABEL_55;
              goto LABEL_62;
            }
LABEL_55:
            ElementData = 0;
            goto LABEL_56;
          }
          v16 = BcdDeleteElement(v28, 352321555);
          ElementData = v16;
          if ( v16 < 0 && v16 != -1073741275 )
            goto LABEL_62;
          v3 = 352321556;
          v17 = BcdDeleteElement(v28, 352321556);
          ElementData = v17;
          if ( v17 < 0 && v17 != -1073741275 )
            goto LABEL_62;
          v3 = 352321557;
LABEL_43:
          v20 = BcdDeleteElement(v28, v3);
          ElementData = v20;
          if ( v20 < 0 && v20 != -1073741275 )
            goto LABEL_62;
          v3 = 352321562;
          v21 = BcdDeleteElement(v28, 352321562);
          ElementData = v21;
          if ( v21 < 0 && v21 != -1073741275 )
            goto LABEL_62;
          v3 = 352321563;
          v22 = BcdDeleteElement(v28, 352321563);
          ElementData = v22;
          if ( v22 < 0 && v22 != -1073741275 )
            goto LABEL_62;
          v3 = 369098780;
          v23 = BcdDeleteElement(v28, 369098780);
          ElementData = v23;
          if ( v23 < 0 && v23 != -1073741275 )
            goto LABEL_62;
          v3 = 301989917;
          goto LABEL_52;
        }
        v18 = BcdDeleteElement(v28, 352321555);
        ElementData = v18;
        if ( v18 < 0 && v18 != -1073741275 )
          goto LABEL_62;
        v3 = 352321556;
      }
      else
      {
        v3 = 352321557;
        v26 = BcdDeleteElement(v28, 352321557);
        ElementData = v26;
        if ( v26 < 0 && v26 != -1073741275 )
          goto LABEL_62;
        v3 = 301989913;
      }
      v19 = BcdDeleteElement(v28, v3);
      ElementData = v19;
      if ( v19 < 0 && v19 != -1073741275 )
        goto LABEL_62;
      v3 = 301989910;
      goto LABEL_43;
    }
  }
LABEL_56:
  if ( v28 )
    BcdCloseObject();
  return (unsigned int)ElementData;
}

```

## disassembly

```asm
0x18004df58  mov     [rsp-18h+arg_0], rbx
0x18004df5d  push    rbp
0x18004df5e  push    rsi
0x18004df5f  push    rdi
0x18004df60  mov     rbp, rsp
0x18004df63  sub     rsp, 20h
0x18004df67  mov     rbx, rcx
0x18004df6a  mov     [rbp+arg_8], 0
0x18004df71  mov     ecx, 2
0x18004df76  mov     [rbp+arg_10], 0
0x18004df7e  lea     rdx, aCleaningUpDebu; "Cleaning up debugger settings."
0x18004df85  mov     [rbp+arg_18], 0
0x18004df8d  call    BfspLogMessage
0x18004df92  lea     r8, [rbp+arg_10]
0x18004df96  mov     [rbp+arg_10], 0
0x18004df9e  lea     rdx, GUID_DEBUGGER_SETTINGS_GROUP
0x18004dfa5  mov     rcx, rbx
0x18004dfa8  call    cs:__imp_BcdOpenObject
0x18004dfae  mov     edi, eax
0x18004dfb0  test    eax, eax
0x18004dfb2  js      loc_18004E2A9
0x18004dfb8  mov     rcx, [rbp+arg_10]
0x18004dfbc  mov     edx, 1600000Bh
0x18004dfc1  call    cs:__imp_BcdDeleteElement
0x18004dfc7  mov     rcx, [rbp+arg_10]
0x18004dfcb  lea     r9, [rbp+arg_8]
0x18004dfcf  lea     r8, [rbp+arg_18]
0x18004dfd3  mov     [rbp+arg_8], 8
0x18004dfda  mov     edx, 15000011h
0x18004dfdf  call    cs:__imp_BcdGetElementData
0x18004dfe5  mov     edi, eax
0x18004dfe7  test    eax, eax
0x18004dfe9  js      loc_18004E2A9
0x18004dfef  mov     rax, [rbp+arg_18]
0x18004dff3  mov     rcx, [rbp+arg_10]
0x18004dff7  test    rax, rax
0x18004dffa  jz      loc_18004E2C7
0x18004e000  mov     ebx, 15000013h
0x18004e005  mov     edx, ebx
0x18004e007  sub     rax, 1
0x18004e00b  jz      loc_18004E1E0
0x18004e011  sub     rax, 1
0x18004e015  jz      loc_18004E1A1
0x18004e01b  cmp     rax, 1
0x18004e01f  jz      loc_18004E140
0x18004e025  call    cs:__imp_BcdDeleteElement
0x18004e02b  mov     edi, eax
0x18004e02d  mov     esi, 0C0000225h
0x18004e032  test    eax, eax
0x18004e034  jns     short loc_18004E03E
0x18004e036  cmp     eax, esi
0x18004e038  jnz     loc_18004E2ED
0x18004e03e  mov     rcx, [rbp+arg_10]
0x18004e042  mov     ebx, 15000014h
0x18004e047  mov     edx, ebx
0x18004e049  call    cs:__imp_BcdDeleteElement
0x18004e04f  mov     edi, eax
0x18004e051  test    eax, eax
0x18004e053  jns     short loc_18004E05D
0x18004e055  cmp     eax, esi
0x18004e057  jnz     loc_18004E2ED
0x18004e05d  mov     rcx, [rbp+arg_10]
0x18004e061  mov     ebx, 12000016h
0x18004e066  mov     edx, ebx
0x18004e068  call    cs:__imp_BcdDeleteElement
0x18004e06e  mov     edi, eax
0x18004e070  test    eax, eax
0x18004e072  jns     short loc_18004E07C
0x18004e074  cmp     eax, esi
0x18004e076  jnz     loc_18004E2ED
0x18004e07c  mov     rcx, [rbp+arg_10]
0x18004e080  mov     ebx, 15000015h
0x18004e085  mov     edx, ebx
0x18004e087  call    cs:__imp_BcdDeleteElement
0x18004e08d  mov     edi, eax
0x18004e08f  test    eax, eax
0x18004e091  jns     short loc_18004E09B
0x18004e093  cmp     eax, esi
0x18004e095  jnz     loc_18004E2ED
0x18004e09b  mov     rcx, [rbp+arg_10]
0x18004e09f  mov     ebx, 1500001Ah
0x18004e0a4  mov     edx, ebx
0x18004e0a6  call    cs:__imp_BcdDeleteElement
0x18004e0ac  mov     edi, eax
0x18004e0ae  test    eax, eax
0x18004e0b0  jns     short loc_18004E0BA
0x18004e0b2  cmp     eax, esi
0x18004e0b4  jnz     loc_18004E2ED
0x18004e0ba  mov     rcx, [rbp+arg_10]
0x18004e0be  mov     ebx, 1500001Bh
0x18004e0c3  mov     edx, ebx
0x18004e0c5  call    cs:__imp_BcdDeleteElement
0x18004e0cb  mov     edi, eax
0x18004e0cd  test    eax, eax
0x18004e0cf  jns     short loc_18004E0D9
0x18004e0d1  cmp     eax, esi
0x18004e0d3  jnz     loc_18004E2ED
0x18004e0d9  mov     rcx, [rbp+arg_10]
0x18004e0dd  mov     ebx, 1600001Ch
0x18004e0e2  mov     edx, ebx
0x18004e0e4  call    cs:__imp_BcdDeleteElement
0x18004e0ea  mov     edi, eax
0x18004e0ec  test    eax, eax
0x18004e0ee  jns     short loc_18004E0F8
0x18004e0f0  cmp     eax, esi
0x18004e0f2  jnz     loc_18004E2ED
0x18004e0f8  mov     rcx, [rbp+arg_10]
0x18004e0fc  mov     ebx, 1200001Dh
0x18004e101  mov     edx, ebx
0x18004e103  call    cs:__imp_BcdDeleteElement
0x18004e109  mov     edi, eax
0x18004e10b  test    eax, eax
0x18004e10d  jns     short loc_18004E117
0x18004e10f  cmp     eax, esi
0x18004e111  jnz     loc_18004E2ED
0x18004e117  mov     rcx, [rbp+arg_10]
0x18004e11b  mov     ebx, 12000019h
0x18004e120  mov     edx, ebx
0x18004e122  call    cs:__imp_BcdDeleteElement
0x18004e128  mov     ecx, 80000000h
0x18004e12d  mov     edi, eax
0x18004e12f  add     eax, ecx
0x18004e131  test    ecx, eax
0x18004e133  jnz     loc_18004E2A7
0x18004e139  cmp     edi, esi
0x18004e13b  jmp     loc_18004E2A5
0x18004e140  call    cs:__imp_BcdDeleteElement
0x18004e146  mov     edi, eax
0x18004e148  mov     esi, 0C0000225h
0x18004e14d  test    eax, eax
0x18004e14f  jns     short loc_18004E159
0x18004e151  cmp     eax, esi
0x18004e153  jnz     loc_18004E2ED
0x18004e159  mov     rcx, [rbp+arg_10]
0x18004e15d  mov     ebx, 15000014h
0x18004e162  mov     edx, ebx
0x18004e164  call    cs:__imp_BcdDeleteElement
0x18004e16a  mov     edi, eax
0x18004e16c  test    eax, eax
0x18004e16e  jns     short loc_18004E178
0x18004e170  cmp     eax, esi
0x18004e172  jnz     loc_18004E2ED
0x18004e178  mov     rcx, [rbp+arg_10]
0x18004e17c  mov     ebx, 15000015h
0x18004e181  mov     edx, ebx
0x18004e183  call    cs:__imp_BcdDeleteElement
0x18004e189  mov     edi, eax
0x18004e18b  test    eax, eax
0x18004e18d  jns     short loc_18004E197
0x18004e18f  cmp     eax, esi
0x18004e191  jnz     loc_18004E2ED
0x18004e197  mov     ebx, 12000016h
0x18004e19c  jmp     loc_18004E291
0x18004e1a1  call    cs:__imp_BcdDeleteElement
0x18004e1a7  mov     edi, eax
0x18004e1a9  mov     esi, 0C0000225h
0x18004e1ae  test    eax, eax
0x18004e1b0  jns     short loc_18004E1BA
0x18004e1b2  cmp     eax, esi
0x18004e1b4  jnz     loc_18004E2ED
0x18004e1ba  mov     rcx, [rbp+arg_10]
0x18004e1be  mov     ebx, 15000014h
0x18004e1c3  mov     edx, ebx
0x18004e1c5  call    cs:__imp_BcdDeleteElement
0x18004e1cb  mov     edi, eax
0x18004e1cd  test    eax, eax
0x18004e1cf  jns     short loc_18004E1D9
0x18004e1d1  cmp     eax, esi
0x18004e1d3  jnz     loc_18004E2ED
0x18004e1d9  mov     ebx, 15000015h
0x18004e1de  jmp     short loc_18004E21D
0x18004e1e0  call    cs:__imp_BcdDeleteElement
0x18004e1e6  mov     edi, eax
0x18004e1e8  mov     esi, 0C0000225h
0x18004e1ed  test    eax, eax
0x18004e1ef  jns     short loc_18004E1F9
0x18004e1f1  cmp     eax, esi
0x18004e1f3  jnz     loc_18004E2ED
0x18004e1f9  mov     ebx, 15000014h
0x18004e1fe  mov     rcx, [rbp+arg_10]
0x18004e202  mov     edx, ebx
0x18004e204  call    cs:__imp_BcdDeleteElement
0x18004e20a  mov     edi, eax
0x18004e20c  test    eax, eax
0x18004e20e  jns     short loc_18004E218
0x18004e210  cmp     eax, esi
0x18004e212  jnz     loc_18004E2ED
0x18004e218  mov     ebx, 12000016h
0x18004e21d  mov     rcx, [rbp+arg_10]
0x18004e221  mov     edx, ebx
0x18004e223  call    cs:__imp_BcdDeleteElement
0x18004e229  mov     edi, eax
0x18004e22b  test    eax, eax
0x18004e22d  jns     short loc_18004E237
0x18004e22f  cmp     eax, esi
0x18004e231  jnz     loc_18004E2ED
0x18004e237  mov     rcx, [rbp+arg_10]
0x18004e23b  mov     ebx, 1500001Ah
0x18004e240  mov     edx, ebx
0x18004e242  call    cs:__imp_BcdDeleteElement
0x18004e248  mov     edi, eax
0x18004e24a  test    eax, eax
0x18004e24c  jns     short loc_18004E256
0x18004e24e  cmp     eax, esi
0x18004e250  jnz     loc_18004E2ED
0x18004e256  mov     rcx, [rbp+arg_10]
0x18004e25a  mov     ebx, 1500001Bh
0x18004e25f  mov     edx, ebx
0x18004e261  call    cs:__imp_BcdDeleteElement
0x18004e267  mov     edi, eax
0x18004e269  test    eax, eax
0x18004e26b  jns     short loc_18004E271
0x18004e26d  cmp     eax, esi
0x18004e26f  jnz     short loc_18004E2ED
0x18004e271  mov     rcx, [rbp+arg_10]
0x18004e275  mov     ebx, 1600001Ch
0x18004e27a  mov     edx, ebx
0x18004e27c  call    cs:__imp_BcdDeleteElement
0x18004e282  mov     edi, eax
0x18004e284  test    eax, eax
0x18004e286  jns     short loc_18004E28C
0x18004e288  cmp     eax, esi
0x18004e28a  jnz     short loc_18004E2ED
0x18004e28c  mov     ebx, 1200001Dh
0x18004e291  mov     rcx, [rbp+arg_10]
0x18004e295  mov     edx, ebx
0x18004e297  call    cs:__imp_BcdDeleteElement
0x18004e29d  mov     edi, eax
0x18004e29f  test    eax, eax
0x18004e2a1  jns     short loc_18004E2A7
0x18004e2a3  cmp     eax, esi
0x18004e2a5  jnz     short loc_18004E2ED
0x18004e2a7  xor     edi, edi
0x18004e2a9  mov     rcx, [rbp+arg_10]
0x18004e2ad  test    rcx, rcx
0x18004e2b0  jz      short loc_18004E2B8
0x18004e2b2  call    cs:__imp_BcdCloseObject
0x18004e2b8  mov     rbx, [rsp+20h+arg_0]
0x18004e2bd  mov     eax, edi
0x18004e2bf  add     rsp, 20h
0x18004e2c3  pop     rdi
0x18004e2c4  pop     rsi
0x18004e2c5  pop     rbp
0x18004e2c6  retn
0x18004e2c7  mov     ebx, 15000015h
0x18004e2cc  mov     edx, ebx
0x18004e2ce  call    cs:__imp_BcdDeleteElement
0x18004e2d4  mov     edi, eax
0x18004e2d6  mov     esi, 0C0000225h
0x18004e2db  test    eax, eax
0x18004e2dd  jns     short loc_18004E2E3
0x18004e2df  cmp     eax, esi
0x18004e2e1  jnz     short loc_18004E2ED
0x18004e2e3  mov     ebx, 12000019h
0x18004e2e8  jmp     loc_18004E1FE
0x18004e2ed  mov     r9d, edi
0x18004e2f0  lea     rdx, aFailedToDelete_0; "Failed to delete debugger settings elem"...
0x18004e2f7  mov     r8d, ebx
0x18004e2fa  mov     ecx, 4
0x18004e2ff  call    BfspLogMessage
0x18004e304  jmp     short loc_18004E2A9
```
