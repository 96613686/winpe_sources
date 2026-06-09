# SdbpGetRegistryMatchingAttributes

- ea: `0x14005289c`
- end: `0x140052bea`
- name: `SdbpGetRegistryMatchingAttributes`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14002f700`
- `0x140052770`

## callees

- `0x140004445`
- `0x1400273f4`
- `0x14002de90`
- `0x14003d820`
- `0x14003e364`
- `0x14003ef10`
- `0x14003f570`
- `0x14003fc10`
- `0x14004007c`
- `0x14005289c`

## string_xrefs

- `0x140052919`: `Failed to get key path tag`
- `0x140052bbd`: `SdbpGetRegistryMatchingAttributes`
- `0x140052bb0`: `Failed to read key path`
- `0x1400529c4`: `Failed to read value type`
- `0x140052b2a`: `Failed to read value data`
- `0x140052ba1`: `Failed to read value data`
- `0x140052b51`: `Failed to read value data size`
- `0x140052a04`: `Unknown registry value type`

## pseudocode

```c
__int64 __fastcall SdbpGetRegistryMatchingAttributes(
        void *a1,
        __int64 a2,
        __int16 **a3,
        __int64 *a4,
        _DWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        __int64 *a8,
        __int64 *a9,
        _QWORD *a10)
{
  __int64 TagDataSize; // rbp
  unsigned int v11; // edi
  unsigned int v13; // r13d
  unsigned int FirstTag; // eax
  __int64 StringTagPtr; // rax
  __int16 *v16; // rsi
  __int16 UShortFromUser; // ax
  int v18; // r14d
  __int64 v19; // r12
  __int64 BinaryTagData; // r15
  unsigned int v21; // eax
  unsigned int v22; // eax
  int DWORDTag; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  __int64 QWORDTag; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // edi
  unsigned int v34; // eax
  int v36; // [rsp+20h] [rbp-58h]
  __int64 v37; // [rsp+30h] [rbp-48h]

  TagDataSize = 0;
  *a3 = 0;
  v11 = a2;
  *a4 = 0;
  v13 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( FirstTag )
  {
    StringTagPtr = SdbGetStringTagPtr(a1, FirstTag);
    v16 = (__int16 *)StringTagPtr;
    if ( !StringTagPtr
      || (!(unsigned __int8)MmIsUserAddress_0(StringTagPtr)
        ? (UShortFromUser = *v16)
        : (UShortFromUser = RtlReadUShortFromUser(v16)),
          !UShortFromUser) )
    {
      AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1054, "Failed to read key path");
      return v13;
    }
    v37 = 0;
    v36 = 0;
    v18 = 0;
    v19 = 0;
    BinaryTagData = 0;
    v21 = SdbFindFirstTag(a1, v11, 24624);
    if ( v21 )
      v37 = SdbGetStringTagPtr(a1, v21);
    v22 = SdbFindFirstTag(a1, v11, 16465);
    if ( v22 )
    {
      DWORDTag = SdbReadDWORDTag(a1, v22, 0);
      v18 = DWORDTag;
      if ( !DWORDTag )
      {
        AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1073, "Failed to read value type", 0);
        return v13;
      }
      v24 = DWORDTag - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( !v26 )
          {
            v32 = SdbFindFirstTag(a1, v11, 36882);
            v33 = v32;
            if ( !v32 )
            {
              AslLogCallPrintf(
                1,
                "SdbpGetRegistryMatchingAttributes",
                1120,
                "Failed to get TAG_REG_VALUE_DATA_BINARY",
                0);
              return v13;
            }
            BinaryTagData = SdbGetBinaryTagData(a1, v32);
            if ( !BinaryTagData )
            {
              AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1126, "Failed to read value data", 0);
              return v13;
            }
            TagDataSize = (unsigned int)SdbGetTagDataSize(a1, v33);
            if ( TagDataSize == 0x20000000 )
            {
              AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1132, "Failed to read value data size", 0);
              return v13;
            }
            QWORDTag = 0;
            goto LABEL_27;
          }
          v27 = v26 - 1;
          if ( !v27 )
          {
            v31 = SdbFindFirstTag(a1, v11, 16466);
            if ( !v31 )
            {
              AslLogCallPrintf(
                1,
                "SdbpGetRegistryMatchingAttributes",
                1100,
                "Failed to get TAG_REG_VALUE_DATA_DWORD",
                0);
              return v13;
            }
            v36 = SdbReadDWORDTag(a1, v31, 0);
            goto LABEL_26;
          }
          v28 = v27 - 3;
          if ( v28 )
          {
            if ( v28 != 4 )
            {
              AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1138, "Unknown registry value type", 0);
              return v13;
            }
            v29 = SdbFindFirstTag(a1, v11, 20507);
            if ( !v29 )
            {
              AslLogCallPrintf(
                1,
                "SdbpGetRegistryMatchingAttributes",
                1110,
                "Failed to get TAG_REG_VALUE_DATA_QWORD",
                0);
              return v13;
            }
            QWORDTag = SdbReadQWORDTag(a1, v29, 0);
LABEL_27:
            v13 = 1;
            *a3 = v16;
            *a4 = v37;
            *a5 = v18;
            *a6 = v19;
            *a7 = v36;
            *a8 = QWORDTag;
            *a9 = BinaryTagData;
            *a10 = TagDataSize;
            return v13;
          }
        }
      }
      v34 = SdbFindFirstTag(a1, v11, 24625);
      if ( !v34 )
      {
        AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1086, "Failed to get TAG_REG_VALUE_DATA_SZ", 0);
        return v13;
      }
      v19 = SdbGetStringTagPtr(a1, v34);
      if ( !v19 )
      {
        AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1092, "Failed to read value data", 0);
        return v13;
      }
    }
LABEL_26:
    QWORDTag = 0;
    goto LABEL_27;
  }
  AslLogCallPrintf(1, "SdbpGetRegistryMatchingAttributes", 1042, "Failed to get key path tag");
  return v13;
}

```

## disassembly

```asm
0x14005289c  mov     [rsp+arg_0], rbx
0x1400528a1  mov     [rsp+arg_18], r9
0x1400528a6  mov     [rsp+arg_10], r8
0x1400528ab  push    rbp
0x1400528ac  push    rsi
0x1400528ad  push    rdi
0x1400528ae  push    r12
0x1400528b0  push    r13
0x1400528b2  push    r14
0x1400528b4  push    r15
0x1400528b6  sub     rsp, 40h
0x1400528ba  mov     rax, [rsp+78h+arg_20]
0x1400528c2  xor     ebp, ebp
0x1400528c4  mov     [r8], rbp
0x1400528c7  mov     edi, edx
0x1400528c9  mov     r8d, 6001h
0x1400528cf  mov     [r9], rbp
0x1400528d2  mov     rbx, rcx
0x1400528d5  mov     r13d, ebp
0x1400528d8  mov     [rax], ebp
0x1400528da  mov     rax, [rsp+78h+arg_28]
0x1400528e2  mov     [rax], rbp
0x1400528e5  mov     rax, [rsp+78h+arg_30]
0x1400528ed  mov     [rax], ebp
0x1400528ef  mov     rax, [rsp+78h+arg_38]
0x1400528f7  mov     [rax], rbp
0x1400528fa  mov     rax, [rsp+78h+arg_40]
0x140052902  mov     [rax], rbp
0x140052905  mov     rax, [rsp+78h+arg_48]
0x14005290d  mov     [rax], rbp
0x140052910  call    SdbFindFirstTag
0x140052915  test    eax, eax
0x140052917  jnz     short loc_14005292B
0x140052919  lea     r9, aFailedToGetKey; "Failed to get key path tag"
0x140052920  mov     r8d, 412h
0x140052926  jmp     loc_140052BBD
0x14005292b  mov     edx, eax
0x14005292d  mov     rcx, rbx
0x140052930  call    SdbGetStringTagPtr
0x140052935  mov     rsi, rax
0x140052938  test    rax, rax
0x14005293b  jz      loc_140052BB0
0x140052941  mov     rcx, rax
0x140052944  call    MmIsUserAddress_0
0x140052949  test    al, al
0x14005294b  jz      short loc_140052957
0x14005294d  mov     rcx, rsi
0x140052950  call    RtlReadUShortFromUser
0x140052955  jmp     short loc_14005295A
0x140052957  movzx   eax, word ptr [rsi]
0x14005295a  test    ax, ax
0x14005295d  jz      loc_140052BB0
0x140052963  mov     r8d, 6030h
0x140052969  mov     [rsp+78h+var_48], rbp
0x14005296e  mov     edx, edi
0x140052970  mov     [rsp+78h+var_58], ebp
0x140052974  mov     rcx, rbx
0x140052977  mov     r14d, ebp
0x14005297a  mov     r12, rbp
0x14005297d  mov     r15, rbp
0x140052980  call    SdbFindFirstTag
0x140052985  test    eax, eax
0x140052987  jz      short loc_140052998
0x140052989  mov     edx, eax
0x14005298b  mov     rcx, rbx
0x14005298e  call    SdbGetStringTagPtr
0x140052993  mov     [rsp+78h+var_48], rax
0x140052998  mov     r8d, 4051h
0x14005299e  mov     edx, edi
0x1400529a0  mov     rcx, rbx
0x1400529a3  call    SdbFindFirstTag
0x1400529a8  test    eax, eax
0x1400529aa  jz      loc_140052A82
0x1400529b0  xor     r8d, r8d
0x1400529b3  mov     edx, eax
0x1400529b5  mov     rcx, rbx
0x1400529b8  call    SdbReadDWORDTag
0x1400529bd  mov     r14d, eax
0x1400529c0  test    eax, eax
0x1400529c2  jnz     short loc_1400529D6
0x1400529c4  lea     r9, aFailedToReadVa_1; "Failed to read value type"
0x1400529cb  mov     r8d, 431h
0x1400529d1  jmp     loc_140052BBD
0x1400529d6  sub     eax, 1
0x1400529d9  jz      loc_140052B68
0x1400529df  sub     eax, 1
0x1400529e2  jz      loc_140052B68
0x1400529e8  sub     eax, 1
0x1400529eb  jz      loc_140052AF0
0x1400529f1  sub     eax, 1
0x1400529f4  jz      short loc_140052A4B
0x1400529f6  sub     eax, 3
0x1400529f9  jz      loc_140052B68
0x1400529ff  cmp     eax, 4
0x140052a02  jz      short loc_140052A16
0x140052a04  lea     r9, aUnknownRegistr_0; "Unknown registry value type"
0x140052a0b  mov     r8d, 472h
0x140052a11  jmp     loc_140052BBD
0x140052a16  mov     r8d, 501Bh
0x140052a1c  mov     edx, edi
0x140052a1e  mov     rcx, rbx
0x140052a21  call    SdbFindFirstTag
0x140052a26  test    eax, eax
0x140052a28  jnz     short loc_140052A3C
0x140052a2a  lea     r9, aFailedToGetTag_1; "Failed to get TAG_REG_VALUE_DATA_QWORD"
0x140052a31  mov     r8d, 456h
0x140052a37  jmp     loc_140052BBD
0x140052a3c  xor     r8d, r8d
0x140052a3f  mov     edx, eax
0x140052a41  mov     rcx, rbx
0x140052a44  call    SdbReadQWORDTag
0x140052a49  jmp     short loc_140052A85
0x140052a4b  mov     r8d, 4052h
0x140052a51  mov     edx, edi
0x140052a53  mov     rcx, rbx
0x140052a56  call    SdbFindFirstTag
0x140052a5b  test    eax, eax
0x140052a5d  jnz     short loc_140052A71
0x140052a5f  lea     r9, aFailedToGetTag_2; "Failed to get TAG_REG_VALUE_DATA_DWORD"
0x140052a66  mov     r8d, 44Ch
0x140052a6c  jmp     loc_140052BBD
0x140052a71  xor     r8d, r8d
0x140052a74  mov     edx, eax
0x140052a76  mov     rcx, rbx
0x140052a79  call    SdbReadDWORDTag
0x140052a7e  mov     [rsp+78h+var_58], eax
0x140052a82  mov     rax, rbp
0x140052a85  mov     rcx, [rsp+78h+arg_10]
0x140052a8d  mov     r13d, 1
0x140052a93  mov     rdx, [rsp+78h+arg_18]
0x140052a9b  mov     [rcx], rsi
0x140052a9e  mov     rcx, [rsp+78h+var_48]
0x140052aa3  mov     [rdx], rcx
0x140052aa6  mov     rcx, [rsp+78h+arg_20]
0x140052aae  mov     rdx, [rsp+78h+arg_30]
0x140052ab6  mov     [rcx], r14d
0x140052ab9  mov     rcx, [rsp+78h+arg_28]
0x140052ac1  mov     [rcx], r12
0x140052ac4  mov     ecx, [rsp+78h+var_58]
0x140052ac8  mov     [rdx], ecx
0x140052aca  mov     rcx, [rsp+78h+arg_38]
0x140052ad2  mov     [rcx], rax
0x140052ad5  mov     rax, [rsp+78h+arg_40]
0x140052add  mov     [rax], r15
0x140052ae0  mov     rax, [rsp+78h+arg_48]
0x140052ae8  mov     [rax], rbp
0x140052aeb  jmp     loc_140052BCE
0x140052af0  mov     r8d, 9012h
0x140052af6  mov     edx, edi
0x140052af8  mov     rcx, rbx
0x140052afb  call    SdbFindFirstTag
0x140052b00  mov     edi, eax
0x140052b02  test    eax, eax
0x140052b04  jnz     short loc_140052B18
0x140052b06  lea     r9, aFailedToGetTag; "Failed to get TAG_REG_VALUE_DATA_BINARY"
0x140052b0d  mov     r8d, 460h
0x140052b13  jmp     loc_140052BBD
0x140052b18  mov     edx, edi
0x140052b1a  mov     rcx, rbx
0x140052b1d  call    SdbGetBinaryTagData
0x140052b22  mov     r15, rax
0x140052b25  test    rax, rax
0x140052b28  jnz     short loc_140052B3C
0x140052b2a  lea     r9, aFailedToReadVa_4; "Failed to read value data"
0x140052b31  mov     r8d, 466h
0x140052b37  jmp     loc_140052BBD
0x140052b3c  mov     edx, edi
0x140052b3e  mov     rcx, rbx
0x140052b41  call    SdbGetTagDataSize
0x140052b46  mov     ebp, eax
0x140052b48  cmp     rbp, 20000000h
0x140052b4f  jnz     short loc_140052B60
0x140052b51  lea     r9, aFailedToReadVa_3; "Failed to read value data size"
0x140052b58  mov     r8d, 46Ch
0x140052b5e  jmp     short loc_140052BBD
0x140052b60  mov     rax, r12
0x140052b63  jmp     loc_140052A85
0x140052b68  mov     r8d, 6031h
0x140052b6e  mov     edx, edi
0x140052b70  mov     rcx, rbx
0x140052b73  call    SdbFindFirstTag
0x140052b78  test    eax, eax
0x140052b7a  jnz     short loc_140052B8B
0x140052b7c  lea     r9, aFailedToGetTag_3; "Failed to get TAG_REG_VALUE_DATA_SZ"
0x140052b83  mov     r8d, 43Eh
0x140052b89  jmp     short loc_140052BBD
0x140052b8b  mov     edx, eax
0x140052b8d  mov     rcx, rbx
0x140052b90  call    SdbGetStringTagPtr
0x140052b95  mov     r12, rax
0x140052b98  test    rax, rax
0x140052b9b  jnz     loc_140052A82
0x140052ba1  lea     r9, aFailedToReadVa_4; "Failed to read value data"
0x140052ba8  mov     r8d, 444h
0x140052bae  jmp     short loc_140052BBD
0x140052bb0  lea     r9, aFailedToReadKe_1; "Failed to read key path"
0x140052bb7  mov     r8d, 41Eh
0x140052bbd  lea     rdx, aSdbpgetregistr; "SdbpGetRegistryMatchingAttributes"
0x140052bc4  mov     ecx, 1
0x140052bc9  call    AslLogCallPrintf
0x140052bce  mov     rbx, [rsp+78h+arg_0]
0x140052bd6  mov     eax, r13d
0x140052bd9  add     rsp, 40h
0x140052bdd  pop     r15
0x140052bdf  pop     r14
0x140052be1  pop     r13
0x140052be3  pop     r12
0x140052be5  pop     rdi
0x140052be6  pop     rsi
0x140052be7  pop     rbp
0x140052be8  retn
```
