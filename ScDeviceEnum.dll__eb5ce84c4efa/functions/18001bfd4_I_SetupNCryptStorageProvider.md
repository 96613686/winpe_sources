# I_SetupNCryptStorageProvider

- ea: `0x18001bfd4`
- end: `0x18001c14f`
- name: `I_SetupNCryptStorageProvider`
- size: `379`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013ca8`
- `0x180014854`
- `0x180016500`
- `0x180016958`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001bfd4`
- `0x18001cc6c`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x18001c0b0`
- `ncrypt!NCryptSetProperty` at `0x18001c0b0`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001c042`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001c042`

## string_xrefs

- `0x18001c0a1`: `SmartCardReader`

## pseudocode

```c
__int64 __fastcall I_SetupNCryptStorageProvider(__int64 a1)
{
  PVOID v2; // rcx
  __int64 v3; // rcx
  SECURITY_STATUS v4; // esi
  BYTE *v5; // r8
  __int64 v6; // r9
  SECURITY_STATUS v7; // ebx

  WppTraceIndent(a1, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( !*(_QWORD *)(a1 + 136) )
  {
    v4 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)(a1 + 136), *(LPCWSTR *)(a1 + 88), 0);
    if ( v4 )
    {
      WppTraceIndent(v3, 2);
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          v4);
      }
    }
    else
    {
      v5 = *(BYTE **)a1;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&v5[2 * v6] );
      v7 = NCryptSetProperty(*(_QWORD *)(a1 + 136), L"SmartCardReader", v5, 2 * v6 + 2, 0x40u);
      if ( v7 )
      {
        WppTraceIndent(v2, 2);
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v7);
        }
      }
    }
  }
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bfd4  push    rbx
0x18001bfd6  push    rsi
0x18001bfd7  push    rdi
0x18001bfd8  push    r14
0x18001bfda  push    r15
0x18001bfdc  sub     rsp, 30h
0x18001bfe0  xor     edx, edx
0x18001bfe2  mov     rbx, rcx
0x18001bfe5  call    WppTraceIndent
0x18001bfea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bff1  lea     r15, WPP_GLOBAL_Control
0x18001bff8  cmp     rcx, r15
0x18001bffb  jz      short loc_18001C025
0x18001bffd  test    byte ptr [rcx+1Ch], 2
0x18001c001  jz      short loc_18001C025
0x18001c003  cmp     byte ptr [rcx+19h], 5
0x18001c007  jb      short loc_18001C025
0x18001c009  mov     r9, cs:WPP_pszIndent
0x18001c010  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001c017  mov     rcx, [rcx+10h]
0x18001c01b  mov     edx, 10h
0x18001c020  call    WPP_SF_s
0x18001c025  lea     rdi, [rbx+88h]
0x18001c02c  xor     r14d, r14d
0x18001c02f  cmp     [rdi], r14
0x18001c032  jnz     loc_18001C0FE
0x18001c038  mov     rdx, [rbx+58h]; pszProviderName
0x18001c03c  xor     r8d, r8d; dwFlags
0x18001c03f  mov     rcx, rdi; phProvider
0x18001c042  call    cs:__imp_NCryptOpenStorageProvider
0x18001c048  mov     esi, eax
0x18001c04a  test    eax, eax
0x18001c04c  jz      short loc_18001C085
0x18001c04e  lea     edx, [r14+2]
0x18001c052  call    WppTraceIndent
0x18001c057  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c05e  cmp     rcx, r15
0x18001c061  jz      loc_18001C0FE
0x18001c067  test    byte ptr [rcx+1Ch], 1
0x18001c06b  jz      loc_18001C0FE
0x18001c071  cmp     byte ptr [rcx+19h], 2
0x18001c075  jb      loc_18001C0FE
0x18001c07b  lea     edx, [r14+11h]
0x18001c07f  mov     [rsp+58h+dwFlags], esi
0x18001c083  jmp     short loc_18001C0E7
0x18001c085  mov     r8, [rbx]; pbInput
0x18001c088  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c08c  inc     r9
0x18001c08f  cmp     [r8+r9*2], r14w
0x18001c094  jnz     short loc_18001C08C
0x18001c096  mov     rcx, [rdi]; hObject
0x18001c099  lea     r9d, ds:2[r9*2]; cbInput
0x18001c0a1  lea     rdx, aSmartcardreade; "SmartCardReader"
0x18001c0a8  mov     [rsp+58h+dwFlags], 40h ; '@'; dwFlags
0x18001c0b0  call    cs:__imp_NCryptSetProperty
0x18001c0b6  mov     ebx, eax
0x18001c0b8  test    eax, eax
0x18001c0ba  jz      short loc_18001C0FE
0x18001c0bc  mov     edx, 2
0x18001c0c1  call    WppTraceIndent
0x18001c0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0cd  cmp     rcx, r15
0x18001c0d0  jz      short loc_18001C0FE
0x18001c0d2  test    byte ptr [rcx+1Ch], 1
0x18001c0d6  jz      short loc_18001C0FE
0x18001c0d8  cmp     byte ptr [rcx+19h], 2
0x18001c0dc  jb      short loc_18001C0FE
0x18001c0de  mov     edx, 12h
0x18001c0e3  mov     [rsp+58h+dwFlags], ebx
0x18001c0e7  mov     r9, cs:WPP_pszIndent
0x18001c0ee  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001c0f5  mov     rcx, [rcx+10h]
0x18001c0f9  call    WPP_SF_sd
0x18001c0fe  mov     edx, 1
0x18001c103  call    WppTraceIndent
0x18001c108  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c10f  cmp     rcx, r15
0x18001c112  jz      short loc_18001C141
0x18001c114  test    byte ptr [rcx+1Ch], 2
0x18001c118  jz      short loc_18001C141
0x18001c11a  cmp     byte ptr [rcx+19h], 5
0x18001c11e  jb      short loc_18001C141
0x18001c120  mov     r9, cs:WPP_pszIndent
0x18001c127  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001c12e  mov     rcx, [rcx+10h]
0x18001c132  mov     edx, 13h
0x18001c137  mov     [rsp+58h+dwFlags], r14d
0x18001c13c  call    WPP_SF_sd
0x18001c141  xor     eax, eax
0x18001c143  add     rsp, 30h
0x18001c147  pop     r15
0x18001c149  pop     r14
0x18001c14b  pop     rdi
0x18001c14c  pop     rsi
0x18001c14d  pop     rbx
0x18001c14e  retn
```
