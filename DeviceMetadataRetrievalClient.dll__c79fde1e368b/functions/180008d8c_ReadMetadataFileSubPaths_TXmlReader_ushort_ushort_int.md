# ReadMetadataFileSubPaths(TXmlReader *,ushort * *,ushort * *,int *)

- ea: `0x180008d8c`
- end: `0x180009133`
- name: `?ReadMetadataFileSubPaths@@YAJPEAVTXmlReader@@PEAPEAG1PEAH@Z`
- size: `935`
- prototype: `__int64 __fastcall(struct TXmlReader *this, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000913c`

## callees

- `0x180008d8c`
- `0x18000c17c`
- `0x18000eed0`
- `0x1800108d8`
- `0x180010a30`
- `0x180010a84`
- `0x180010bc8`
- `0x180010c40`
- `0x180010e08`
- `0x1800136d2`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009006`
- `KERNEL32!GetProcessHeap` at `0x180009023`
- `KERNEL32!GetProcessHeap` at `0x180009006`
- `KERNEL32!GetProcessHeap` at `0x180009023`
- `KERNEL32!HeapFree` at `0x180009014`
- `KERNEL32!HeapFree` at `0x180009031`
- `KERNEL32!HeapFree` at `0x180009014`
- `KERNEL32!HeapFree` at `0x180009031`

## string_xrefs

- `0x180008db7`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180008e15`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180008efc`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180008f66`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180008f86`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180008faf`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180008e69`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x180008e81`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x180008e99`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceStage/2008/1/`

## pseudocode

```c
__int64 __fastcall ReadMetadataFileSubPaths(
        struct TXmlReader *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        int *a4)
{
  unsigned __int16 **v4; // rsi
  unsigned int StartElement; // ebx
  int v8; // r8d
  unsigned __int16 *v9; // r15
  unsigned __int16 *v10; // rbp
  int v11; // r12d
  const unsigned __int16 *v12; // r8
  const wchar_t *v13; // rbx
  int v14; // esi
  _QWORD *v15; // rcx
  int v16; // edx
  const unsigned __int16 *v17; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  wchar_t *String1[2]; // [rsp+30h] [rbp-38h] BYREF

  v4 = a3;
  String1[0] = 0;
  StartElement = TXmlReader::ReadStartElement(
                   this,
                   L"PackageStructure",
                   L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
  if ( StartElement )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, v8, (unsigned int)L"PackageStructure", StartElement);
    return StartElement;
  }
  v9 = 0;
  v10 = 0;
  v11 = 0;
  StartElement = TXmlReader::IsNodeQName(
                   this,
                   L"Metadata",
                   L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
  if ( StartElement == 1 )
  {
LABEL_33:
    StartElement = TXmlReader::ReadEndElement(
                     this,
                     L"PackageStructure",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( !StartElement )
    {
      *v4 = v10;
      *a4 = v11;
      *a2 = v9;
      return StartElement;
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    v16 = 98;
    v17 = L"PackageStructure";
LABEL_37:
    WPP_SF_Sd(v15[2], v16, (_DWORD)v12, (_DWORD)v17, StartElement);
    goto LABEL_38;
  }
  while ( 1 )
  {
    if ( StartElement )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 93;
        goto LABEL_45;
      }
      goto LABEL_38;
    }
    StartElement = TXmlReader::ReadAttributeString(this, L"MetadataID", v12, (const unsigned __int16 **)String1);
    if ( StartElement )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v16 = 94;
      v17 = L"MetadataID";
      goto LABEL_37;
    }
    v13 = String1[0];
    if ( !wcscmp_0(String1[0], L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/") )
      v14 = 1;
    else
      v14 = !wcscmp_0(v13, L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo")
          ? 2
          : wcscmp_0(v13, L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceStage/2008/1/") == 0
          ? 3
          : 0;
    StartElement = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 88LL))(*(_QWORD *)this);
    if ( StartElement )
      break;
    if ( v14 && (v14 != 1 || !v9) && (v14 != 2 || !v10) && (v14 != 3 || !v11) )
    {
      StartElement = TXmlReader::ReadElementString(
                       this,
                       L"Metadata",
                       L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/",
                       (const unsigned __int16 **)String1);
      if ( !StartElement )
      {
        switch ( v14 )
        {
          case 1:
            v9 = MemMallocAndCopy(String1[0]);
            if ( !v9 )
            {
              StartElement = -2147024882;
              goto LABEL_40;
            }
            break;
          case 2:
            v10 = MemMallocAndCopy(String1[0]);
            if ( !v10 )
            {
              StartElement = -2147024882;
              goto LABEL_38;
            }
            break;
          case 3:
            v11 = 1;
            break;
        }
        goto LABEL_31;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v16 = 97;
LABEL_45:
      v17 = L"Metadata";
      goto LABEL_37;
    }
    StartElement = TXmlReader::SkipElement(
                     this,
                     L"Metadata",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( StartElement )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_38;
      v16 = 96;
      goto LABEL_45;
    }
LABEL_31:
    StartElement = TXmlReader::IsNodeQName(
                     this,
                     L"Metadata",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( StartElement == 1 )
    {
      v4 = a3;
      goto LABEL_33;
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v16 = 95;
    goto LABEL_45;
  }
LABEL_38:
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
LABEL_40:
  if ( v10 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v10);
  }
  return StartElement;
}

```

## disassembly

```asm
0x180008d8c  mov     rax, rsp
0x180008d8f  mov     [rax+8], rbx
0x180008d93  mov     [rax+20h], rbp
0x180008d97  mov     [rax+18h], r8
0x180008d9b  mov     [rax+10h], rdx
0x180008d9f  push    rsi
0x180008da0  push    r12
0x180008da2  push    r13
0x180008da4  push    r14
0x180008da6  push    r15
0x180008da8  sub     rsp, 40h
0x180008dac  mov     rsi, r8
0x180008daf  mov     qword ptr [rax-38h], 0
0x180008db7  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008dbe  mov     r13, r9
0x180008dc1  lea     rdx, aPackagestructu; "PackageStructure"
0x180008dc8  mov     r14, rcx
0x180008dcb  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x180008dd0  mov     ebx, eax
0x180008dd2  test    eax, eax
0x180008dd4  jz      short loc_180008E15
0x180008dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ddd  lea     rax, WPP_GLOBAL_Control
0x180008de4  cmp     rcx, rax
0x180008de7  jz      loc_180009117
0x180008ded  test    byte ptr [rcx+1Ch], 1
0x180008df1  jz      loc_180009117
0x180008df7  mov     rcx, [rcx+10h]
0x180008dfb  lea     r9, aPackagestructu; "PackageStructure"
0x180008e02  mov     edx, 5Ch ; '\'
0x180008e07  mov     [rsp+68h+var_48], ebx
0x180008e0b  call    WPP_SF_Sd
0x180008e10  jmp     loc_180009117
0x180008e15  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008e1c  mov     rcx, r14; this
0x180008e1f  lea     rdx, aMetadata; "Metadata"
0x180008e26  xor     r15d, r15d
0x180008e29  xor     ebp, ebp
0x180008e2b  xor     r12d, r12d
0x180008e2e  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x180008e33  mov     ebx, eax
0x180008e35  cmp     eax, 1
0x180008e38  jz      loc_180008FAF
0x180008e3e  test    ebx, ebx
0x180008e40  jnz     loc_1800090DD
0x180008e46  lea     r9, [rsp+68h+String1]; unsigned __int16 **
0x180008e4b  mov     rcx, r14; this
0x180008e4e  lea     rdx, aMetadataid; "MetadataID"
0x180008e55  call    ?ReadAttributeString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadAttributeString(ushort const *,ushort const *,ushort const * *)
0x180008e5a  mov     ebx, eax
0x180008e5c  test    eax, eax
0x180008e5e  jnz     loc_1800090AB
0x180008e64  mov     rbx, [rsp+68h+String1]
0x180008e69  lea     rdx, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x180008e70  mov     rcx, rbx; String1
0x180008e73  call    wcscmp_0
0x180008e78  test    eax, eax
0x180008e7a  jnz     short loc_180008E81
0x180008e7c  lea     esi, [rax+1]
0x180008e7f  jmp     short loc_180008EB1
0x180008e81  lea     rdx, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x180008e88  mov     rcx, rbx; String1
0x180008e8b  call    wcscmp_0
0x180008e90  test    eax, eax
0x180008e92  jnz     short loc_180008E99
0x180008e94  lea     esi, [rax+2]
0x180008e97  jmp     short loc_180008EB1
0x180008e99  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/De"...
0x180008ea0  mov     rcx, rbx; String1
0x180008ea3  call    wcscmp_0
0x180008ea8  neg     eax
0x180008eaa  sbb     esi, esi
0x180008eac  not     esi
0x180008eae  and     esi, 3
0x180008eb1  mov     rcx, [r14]
0x180008eb4  mov     rax, [rcx]
0x180008eb7  mov     rax, [rax+58h]
0x180008ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec0  mov     ebx, eax
0x180008ec2  test    eax, eax
0x180008ec4  jnz     loc_180009083
0x180008eca  test    esi, esi
0x180008ecc  jz      loc_180008F66
0x180008ed2  cmp     esi, 1
0x180008ed5  jnz     short loc_180008EE0
0x180008ed7  test    r15, r15
0x180008eda  jnz     loc_180008F66
0x180008ee0  cmp     esi, 2
0x180008ee3  jnz     short loc_180008EEA
0x180008ee5  test    rbp, rbp
0x180008ee8  jnz     short loc_180008F66
0x180008eea  cmp     esi, 3
0x180008eed  jnz     short loc_180008EF4
0x180008eef  test    r12d, r12d
0x180008ef2  jnz     short loc_180008F66
0x180008ef4  lea     r9, [rsp+68h+String1]; unsigned __int16 **
0x180008ef9  mov     rcx, r14; this
0x180008efc  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008f03  lea     rdx, aMetadata; "Metadata"
0x180008f0a  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x180008f0f  mov     ebx, eax
0x180008f11  test    eax, eax
0x180008f13  jnz     loc_18000903C
0x180008f19  cmp     esi, 1
0x180008f1c  jnz     short loc_180008F3A
0x180008f1e  mov     rcx, [rsp+68h+String1]; unsigned __int16 *
0x180008f23  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x180008f28  mov     r15, rax
0x180008f2b  test    rax, rax
0x180008f2e  jnz     short loc_180008F86
0x180008f30  mov     ebx, 8007000Eh
0x180008f35  jmp     loc_18000901A
0x180008f3a  cmp     esi, 2
0x180008f3d  jnz     short loc_180008F5B
0x180008f3f  mov     rcx, [rsp+68h+String1]; unsigned __int16 *
0x180008f44  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x180008f49  mov     rbp, rax
0x180008f4c  test    rax, rax
0x180008f4f  jnz     short loc_180008F86
0x180008f51  mov     ebx, 8007000Eh
0x180008f56  jmp     loc_180009001
0x180008f5b  cmp     esi, 3
0x180008f5e  jnz     short loc_180008F86
0x180008f60  lea     r12d, [rsi-2]
0x180008f64  jmp     short loc_180008F86
0x180008f66  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008f6d  mov     rcx, r14; this
0x180008f70  lea     rdx, aMetadata; "Metadata"
0x180008f77  call    ?SkipElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::SkipElement(ushort const *,ushort const *)
0x180008f7c  mov     ebx, eax
0x180008f7e  test    eax, eax
0x180008f80  jnz     loc_180009063
0x180008f86  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008f8d  mov     rcx, r14; this
0x180008f90  lea     rdx, aMetadata; "Metadata"
0x180008f97  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x180008f9c  mov     ebx, eax
0x180008f9e  cmp     eax, 1
0x180008fa1  jnz     loc_180008E3E
0x180008fa7  mov     rsi, [rsp+68h+arg_10]
0x180008faf  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180008fb6  mov     rcx, r14; this
0x180008fb9  lea     rdx, aPackagestructu; "PackageStructure"
0x180008fc0  call    ?ReadEndElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadEndElement(ushort const *,ushort const *)
0x180008fc5  mov     ebx, eax
0x180008fc7  test    eax, eax
0x180008fc9  jz      loc_180009108
0x180008fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fd6  lea     rax, WPP_GLOBAL_Control
0x180008fdd  cmp     rcx, rax
0x180008fe0  jz      short loc_180009001
0x180008fe2  test    byte ptr [rcx+1Ch], 1
0x180008fe6  jz      short loc_180009001
0x180008fe8  mov     edx, 62h ; 'b'
0x180008fed  lea     r9, aPackagestructu; "PackageStructure"
0x180008ff4  mov     rcx, [rcx+10h]
0x180008ff8  mov     [rsp+68h+var_48], ebx
0x180008ffc  call    WPP_SF_Sd
0x180009001  test    r15, r15
0x180009004  jz      short loc_18000901A
0x180009006  call    cs:__imp_GetProcessHeap
0x18000900c  mov     r8, r15; lpMem
0x18000900f  xor     edx, edx; dwFlags
0x180009011  mov     rcx, rax; hHeap
0x180009014  call    cs:__imp_HeapFree
0x18000901a  test    rbp, rbp
0x18000901d  jz      loc_180009117
0x180009023  call    cs:__imp_GetProcessHeap
0x180009029  mov     r8, rbp; lpMem
0x18000902c  xor     edx, edx; dwFlags
0x18000902e  mov     rcx, rax; hHeap
0x180009031  call    cs:__imp_HeapFree
0x180009037  jmp     loc_180009117
0x18000903c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009043  lea     rax, WPP_GLOBAL_Control
0x18000904a  cmp     rcx, rax
0x18000904d  jz      short loc_180009001
0x18000904f  test    byte ptr [rcx+1Ch], 1
0x180009053  jz      short loc_180009001
0x180009055  mov     edx, 61h ; 'a'
0x18000905a  lea     r9, aMetadata; "Metadata"
0x180009061  jmp     short loc_180008FF4
0x180009063  mov     rcx, cs:WPP_GLOBAL_Control
0x18000906a  lea     rax, WPP_GLOBAL_Control
0x180009071  cmp     rcx, rax
0x180009074  jz      short loc_180009001
0x180009076  test    byte ptr [rcx+1Ch], 1
0x18000907a  jz      short loc_180009001
0x18000907c  mov     edx, 60h ; '`'
0x180009081  jmp     short loc_18000905A
0x180009083  mov     rcx, cs:WPP_GLOBAL_Control
0x18000908a  lea     rax, WPP_GLOBAL_Control
0x180009091  cmp     rcx, rax
0x180009094  jz      loc_180009001
0x18000909a  test    byte ptr [rcx+1Ch], 1
0x18000909e  jz      loc_180009001
0x1800090a4  mov     edx, 5Fh ; '_'
0x1800090a9  jmp     short loc_18000905A
0x1800090ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090b2  lea     rax, WPP_GLOBAL_Control
0x1800090b9  cmp     rcx, rax
0x1800090bc  jz      loc_180009001
0x1800090c2  test    byte ptr [rcx+1Ch], 1
0x1800090c6  jz      loc_180009001
0x1800090cc  mov     edx, 5Eh ; '^'
0x1800090d1  lea     r9, aMetadataid; "MetadataID"
0x1800090d8  jmp     loc_180008FF4
0x1800090dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090e4  lea     rax, WPP_GLOBAL_Control
0x1800090eb  cmp     rcx, rax
0x1800090ee  jz      loc_180009001
0x1800090f4  test    byte ptr [rcx+1Ch], 1
0x1800090f8  jz      loc_180009001
0x1800090fe  mov     edx, 5Dh ; ']'
0x180009103  jmp     loc_18000905A
0x180009108  mov     rax, [rsp+68h+arg_8]
0x18000910d  mov     [rsi], rbp
0x180009110  mov     [r13+0], r12d
0x180009114  mov     [rax], r15
0x180009117  lea     r11, [rsp+68h+var_28]
0x18000911c  mov     eax, ebx
0x18000911e  mov     rbx, [r11+30h]
0x180009122  mov     rbp, [r11+48h]
0x180009126  mov     rsp, r11
0x180009129  pop     r15
0x18000912b  pop     r14
0x18000912d  pop     r13
0x18000912f  pop     r12
0x180009131  pop     rsi
0x180009132  retn
```
