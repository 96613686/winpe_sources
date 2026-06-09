# BfspCreateBootmgrObject

- ea: `0x18004e544`
- end: `0x18004ea76`
- name: `BfspCreateBootmgrObject`
- size: `1330`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18004f08c`
- `0x180050410`

## callees

- `0x1800078b0`
- `0x18004cdd4`
- `0x18004e544`
- `0x18004f854`
- `0x18004f888`
- `0x180050074`
- `0x1800507fc`
- `0x180050894`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18004e74d`
- `ntdll!RtlStringFromGUID` at `0x18004e74d`
- `ntdll!RtlFreeUnicodeString` at `0x18004e76c`
- `ntdll!RtlFreeUnicodeString` at `0x18004e76c`
- `ntdll!RtlInitUnicodeString` at `0x18004e5c3`
- `ntdll!RtlInitUnicodeString` at `0x18004e5c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ea17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ea30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ea17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ea30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea22`
- `bcd!BcdSetElementData` at `0x18004e784`
- `bcd!BcdSetElementData` at `0x18004e7de`
- `bcd!BcdSetElementData` at `0x18004e80a`
- `bcd!BcdSetElementData` at `0x18004e836`
- `bcd!BcdSetElementData` at `0x18004e952`
- `bcd!BcdSetElementData` at `0x18004e784`
- `bcd!BcdSetElementData` at `0x18004e7de`
- `bcd!BcdSetElementData` at `0x18004e80a`
- `bcd!BcdSetElementData` at `0x18004e836`
- `bcd!BcdSetElementData` at `0x18004e952`
- `bcd!BcdCloseObject` at `0x18004e6bb`
- `bcd!BcdCloseObject` at `0x18004e6c5`
- `bcd!BcdCloseObject` at `0x18004ea3f`
- `bcd!BcdCloseObject` at `0x18004ea4e`
- `bcd!BcdCloseObject` at `0x18004e6bb`
- `bcd!BcdCloseObject` at `0x18004e6c5`
- `bcd!BcdCloseObject` at `0x18004ea3f`
- `bcd!BcdCloseObject` at `0x18004ea4e`
- `bcd!BcdOpenObject` at `0x18004e5fe`
- `bcd!BcdOpenObject` at `0x18004e6a9`
- `bcd!BcdOpenObject` at `0x18004e71c`
- `bcd!BcdOpenObject` at `0x18004e983`
- `bcd!BcdOpenObject` at `0x18004e5fe`
- `bcd!BcdOpenObject` at `0x18004e6a9`
- `bcd!BcdOpenObject` at `0x18004e71c`
- `bcd!BcdOpenObject` at `0x18004e983`
- `bcd!BcdCopyObjects` at `0x18004e6f6`
- `bcd!BcdCopyObjects` at `0x18004e6f6`
- `bcd!BcdGetElementData` at `0x18004e694`
- `bcd!BcdGetElementData` at `0x18004e694`
- `bcd!BcdDeleteElement` at `0x18004e7b1`
- `bcd!BcdDeleteElement` at `0x18004e911`
- `bcd!BcdDeleteElement` at `0x18004e7b1`
- `bcd!BcdDeleteElement` at `0x18004e911`

## string_xrefs

- `0x18004e728`: `Failed to open a handle to the bootmgr object. Status = [%x]`
- `0x18004e702`: `Failed to copy bootmgr object data. Status = [%x]`
- `0x18004e5cf`: `Create BOOTMGR object RetainBootDefault:%c`
- `0x18004e98f`: `Failed to open handle to fwbootmgr object. Status = [%x]`
- `0x18004e871`: `Failed to update bootmgr display order. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateBootmgrObject(__int64 a1, __int64 a2, __int64 a3, GUID *a4)
{
  void *v5; // r14
  unsigned int v6; // r13d
  void *v7; // rsi
  unsigned int v8; // r12d
  unsigned int v9; // edi
  int BcdElementData; // eax
  int v11; // ebx
  int v12; // eax
  unsigned int BcdCopyFlags; // eax
  int v14; // eax
  int v15; // eax
  GUID *v16; // rbx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int inserted; // eax
  __int16 v22; // cx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  char v29; // [rsp+20h] [rbp-79h]
  __int64 v30; // [rsp+28h] [rbp-71h] BYREF
  _WORD v31[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-61h] BYREF
  int v34; // [rsp+3Ch] [rbp-5Dh] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-59h] BYREF
  LPVOID v36; // [rsp+48h] [rbp-51h] BYREF
  __int64 v37; // [rsp+50h] [rbp-49h] BYREF
  __int64 v38; // [rsp+58h] [rbp-41h] BYREF
  __int64 v39; // [rsp+60h] [rbp-39h] BYREF
  GUID *Guid; // [rsp+68h] [rbp-31h]
  __int64 v41; // [rsp+70h] [rbp-29h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-21h] BYREF
  __int64 v43; // [rsp+88h] [rbp-11h]
  __int128 v44; // [rsp+90h] [rbp-9h] BYREF

  v41 = a1;
  v31[0] = 0;
  v37 = 0;
  v34 = 0;
  v39 = 0;
  v30 = 0;
  v44 = 0;
  v5 = 0;
  v36 = 0;
  DestinationString = 0;
  v6 = 0;
  v32 = 0;
  v38 = 0;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  lpMem = 0;
  v33 = 0;
  Guid = a4;
  v43 = a3;
  RtlInitUnicodeString(&DestinationString, 0);
  BfspLogMessage(2, L"Create BOOTMGR object RetainBootDefault:%c", (dword_1800A453C & 0x100) != 0 ? 121 : 110);
  v9 = 1;
  if ( (int)BcdOpenObject(a2, &GUID_WINDOWS_BOOTMGR, &v30) >= 0 )
  {
    BcdElementData = BfspGetBcdElementData(v30, 603979777, &v36, &v32);
    v11 = BcdElementData;
    if ( BcdElementData != -1073741275 )
    {
      v5 = v36;
      if ( BcdElementData < 0 )
        goto LABEL_62;
      v6 = v32;
    }
    v12 = BfspGetBcdElementData(v30, 603979792, &lpMem, &v33);
    v11 = v12;
    if ( v12 == -1073741275 )
    {
      v7 = 0;
    }
    else
    {
      v7 = lpMem;
      if ( v12 < 0 )
        goto LABEL_60;
      v8 = v33;
    }
    if ( (dword_1800A453C & 0x100) != 0 )
    {
      v34 = 16;
      if ( (int)BcdGetElementData(v30, 587202563, &v44, &v34) >= 0 && (int)BcdOpenObject(a2, &v44, &v39) >= 0 )
      {
        v29 = 1;
        BcdCloseObject(v39);
      }
    }
    BcdCloseObject(v30);
    v30 = 0;
  }
  v37 = 0x1010000200000001LL;
  BcdCopyFlags = BfspGetBcdCopyFlags((unsigned int)dword_1800A453C);
  v14 = BcdCopyObjects(v41, &v37, BcdCopyFlags, a2);
  v11 = v14;
  if ( v14 < 0 )
  {
    BfspLogMessage(4, L"Failed to copy bootmgr object data. Status = [%x]", (unsigned int)v14);
    goto LABEL_60;
  }
  v15 = BcdOpenObject(a2, &GUID_WINDOWS_BOOTMGR, &v30);
  v11 = v15;
  if ( v15 < 0 )
  {
    BfspLogMessage(4, L"Failed to open a handle to the bootmgr object. Status = [%x]", (unsigned int)v15);
    goto LABEL_60;
  }
  v16 = (GUID *)&v44;
  if ( !v29 )
    v16 = Guid;
  if ( v16 )
  {
    RtlStringFromGUID(v16, &DestinationString);
    BfspLogMessage(2, L"Setting {default} to %wZ", &DestinationString);
    RtlFreeUnicodeString(&DestinationString);
    v17 = BcdSetElementData(v30, 587202563, v16, 16);
    v11 = v17;
    if ( v17 < 0 )
    {
      BfspLogMessage(4, L"Failed to set default bootmgr object. Status = [%x]", (unsigned int)v17);
      goto LABEL_60;
    }
  }
  else if ( (dword_1800A453C & 0x100) != 0 )
  {
    BcdDeleteElement(v30, 587202563);
  }
  if ( v43 )
  {
    if ( (dword_1800A453C & 0x400) != 0 )
    {
      v18 = BcdSetElementData(v30, 587202566, v43, 16);
      v11 = v18;
      if ( v18 < 0 )
      {
        BfspLogMessage(4, L"Failed to set bootmgr resume object. Status = [%x]", (unsigned int)v18);
        goto LABEL_60;
      }
    }
  }
  if ( v5 )
  {
    v19 = BcdSetElementData(v30, 603979777, v5, v6);
    v11 = v19;
    if ( v19 < 0 )
    {
      BfspLogMessage(4, L"Failed to set bootmgr display order. Status = [%x]", (unsigned int)v19);
      goto LABEL_60;
    }
  }
  if ( v7 )
  {
    v20 = BcdSetElementData(v30, 603979792, v7, v8);
    v11 = v20;
    if ( v20 < 0 )
    {
      BfspLogMessage(4, L"Failed to set bootmgr tools display order. Status = [%x]", (unsigned int)v20);
      goto LABEL_60;
    }
  }
  if ( Guid )
  {
    inserted = BfspInsertObjectInDisplayOrder(v30, 603979777, Guid, 0);
    v11 = inserted;
    if ( inserted < 0 )
    {
      BfspLogMessage(4, L"Failed to update bootmgr display order. Status = [%x]", (unsigned int)inserted);
      goto LABEL_60;
    }
  }
  if ( (dword_1800A453C & 2) == 0
    || (v11 = BfspInsertObjectInDisplayOrder(v30, 603979777, &GUID_WINDOWS_LEGACY_NTLDR, 0), v11 >= 0) )
  {
    if ( (dword_1800A453C & 0x800) == 0
      || (v11 = BfspInsertObjectInDisplayOrder(v30, 603979792, &GUID_WINDOWS_MEMORY_TESTER, 0), v11 >= 0) )
    {
      v11 = BfspSetObjectDeviceAndPath(v41, a2, &GUID_WINDOWS_BOOTMGR, &GUID_WINDOWS_BOOTMGR);
      if ( v11 >= 0 )
      {
        if ( !byte_1800A4538 )
        {
          BcdDeleteElement(v30, 301989890);
LABEL_58:
          v25 = BfspSetLocale(a2, &GUID_WINDOWS_BOOTMGR);
          v11 = v25;
          if ( v25 < 0 )
            BfspLogMessage(4, L"Failed to set {bootmgr} locale. Status = [%x]", (unsigned int)v25);
          goto LABEL_60;
        }
        v22 = dword_1800A453C;
        if ( (dword_1800A453C & 0x220000) == 0x220000 )
        {
          BfspLogMessage(2, L"Setting \"nofirmwaresync\" element for {bootmgr} object");
          LOBYTE(v31[0]) = 1;
          v23 = BcdSetElementData(v30, 369098882, v31, 2);
          v11 = v23;
          if ( v23 < 0 )
          {
            BfspLogMessage(
              4,
              L"Failed to set \"nofirmwaresync\" element for {bootmgr} object. Status = [%x]",
              (unsigned int)v23);
            goto LABEL_60;
          }
          v22 = dword_1800A453C;
        }
        if ( (v22 & 0x10) != 0 )
        {
          if ( (v22 & 0x1080) != 0 )
            BfspLogMessage(
              4,
              L"AddBootmgrLast and PreserveBootOrder options are ignored when custom volume is specified");
          goto LABEL_58;
        }
        v24 = BcdOpenObject(a2, &GUID_FIRMWARE_BOOTMGR, &v38);
        v11 = v24;
        if ( v24 >= 0 )
        {
          if ( (dword_1800A453C & 0x80u) == 0 )
            v9 = ((unsigned int)dword_1800A453C >> 11) & 2;
          v11 = BfspInsertObjectInDisplayOrder(v38, 603979777, &GUID_WINDOWS_BOOTMGR, v9);
          if ( v11 < 0 )
            goto LABEL_60;
          goto LABEL_58;
        }
        BfspLogMessage(4, L"Failed to open handle to fwbootmgr object. Status = [%x]", (unsigned int)v24);
      }
    }
  }
LABEL_60:
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
LABEL_62:
  if ( v5 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v5);
  }
  if ( v30 )
    BcdCloseObject(v30);
  if ( v38 )
    BcdCloseObject(v38);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004e544  push    rbp
0x18004e546  push    rbx
0x18004e547  push    rsi
0x18004e548  push    rdi
0x18004e549  push    r12
0x18004e54b  push    r13
0x18004e54d  push    r14
0x18004e54f  push    r15
0x18004e551  lea     rbp, [rsp-1Fh]
0x18004e556  sub     rsp, 0B8h
0x18004e55d  mov     rax, cs:__security_cookie
0x18004e564  xor     rax, rsp
0x18004e567  mov     [rbp+57h+var_50], rax
0x18004e56b  xor     ebx, ebx
0x18004e56d  mov     [rbp+57h+var_80], rcx
0x18004e571  mov     r15, rdx
0x18004e574  mov     [rbp+57h+var_C0], bx
0x18004e578  xorps   xmm0, xmm0
0x18004e57b  mov     [rbp+57h+var_A0], rbx
0x18004e57f  xorps   xmm1, xmm1
0x18004e582  mov     [rbp+57h+var_B4], ebx
0x18004e585  xor     edx, edx; SourceString
0x18004e587  mov     [rbp+57h+var_90], rbx
0x18004e58b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004e58f  mov     [rbp+57h+var_C8], rbx
0x18004e593  movups  [rbp+57h+var_60], xmm0
0x18004e597  mov     r14d, ebx
0x18004e59a  mov     [rbp+57h+var_A8], rbx
0x18004e59e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18004e5a2  mov     r13d, ebx
0x18004e5a5  mov     [rbp+57h+var_BC], ebx
0x18004e5a8  mov     [rbp+57h+var_98], rbx
0x18004e5ac  mov     esi, ebx
0x18004e5ae  mov     [rbp+57h+var_D0], bl
0x18004e5b1  mov     r12d, ebx
0x18004e5b4  mov     [rbp+57h+lpMem], rbx
0x18004e5b8  mov     [rbp+57h+var_B8], ebx
0x18004e5bb  mov     [rbp+57h+Guid], r9
0x18004e5bf  mov     [rbp+57h+var_68], r8
0x18004e5c3  call    cs:__imp_RtlInitUnicodeString
0x18004e5c9  mov     eax, cs:dword_1800A453C
0x18004e5cf  lea     rdx, aCreateBootmgrO; "Create BOOTMGR object RetainBootDefault"...
0x18004e5d6  and     eax, 100h
0x18004e5db  lea     ecx, [rbx+2]
0x18004e5de  neg     eax
0x18004e5e0  sbb     r8d, r8d
0x18004e5e3  and     r8d, 0Bh
0x18004e5e7  add     r8d, 6Eh ; 'n'
0x18004e5eb  call    BfspLogMessage
0x18004e5f0  lea     r8, [rbp+57h+var_C8]
0x18004e5f4  mov     rcx, r15
0x18004e5f7  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18004e5fe  call    cs:__imp_BcdOpenObject
0x18004e604  lea     edi, [rbx+1]
0x18004e607  test    eax, eax
0x18004e609  js      loc_18004E6D3
0x18004e60f  mov     rcx, [rbp+57h+var_C8]
0x18004e613  lea     r9, [rbp+57h+var_BC]
0x18004e617  lea     r8, [rbp+57h+var_A8]
0x18004e61b  mov     edx, 24000001h
0x18004e620  call    BfspGetBcdElementData
0x18004e625  mov     esi, 0C0000225h
0x18004e62a  mov     ebx, eax
0x18004e62c  cmp     eax, esi
0x18004e62e  jz      short loc_18004E640
0x18004e630  mov     r14, [rbp+57h+var_A8]
0x18004e634  test    eax, eax
0x18004e636  js      loc_18004EA1D
0x18004e63c  mov     r13d, [rbp+57h+var_BC]
0x18004e640  mov     rcx, [rbp+57h+var_C8]
0x18004e644  lea     r9, [rbp+57h+var_B8]
0x18004e648  lea     r8, [rbp+57h+lpMem]
0x18004e64c  mov     edx, 24000010h
0x18004e651  call    BfspGetBcdElementData
0x18004e656  mov     ebx, eax
0x18004e658  cmp     eax, esi
0x18004e65a  jnz     short loc_18004E660
0x18004e65c  xor     esi, esi
0x18004e65e  jmp     short loc_18004E670
0x18004e660  mov     rsi, [rbp+57h+lpMem]
0x18004e664  test    eax, eax
0x18004e666  js      loc_18004EA04
0x18004e66c  mov     r12d, [rbp+57h+var_B8]
0x18004e670  test    cs:dword_1800A453C, 100h
0x18004e67a  jz      short loc_18004E6C1
0x18004e67c  mov     rcx, [rbp+57h+var_C8]
0x18004e680  lea     r9, [rbp+57h+var_B4]
0x18004e684  lea     r8, [rbp+57h+var_60]
0x18004e688  mov     [rbp+57h+var_B4], 10h
0x18004e68f  mov     edx, 23000003h
0x18004e694  call    cs:__imp_BcdGetElementData
0x18004e69a  test    eax, eax
0x18004e69c  js      short loc_18004E6C1
0x18004e69e  lea     r8, [rbp+57h+var_90]
0x18004e6a2  mov     rcx, r15
0x18004e6a5  lea     rdx, [rbp+57h+var_60]
0x18004e6a9  call    cs:__imp_BcdOpenObject
0x18004e6af  test    eax, eax
0x18004e6b1  js      short loc_18004E6C1
0x18004e6b3  mov     rcx, [rbp+57h+var_90]
0x18004e6b7  mov     [rbp+57h+var_D0], dil
0x18004e6bb  call    cs:__imp_BcdCloseObject
0x18004e6c1  mov     rcx, [rbp+57h+var_C8]
0x18004e6c5  call    cs:__imp_BcdCloseObject
0x18004e6cb  mov     [rbp+57h+var_C8], 0
0x18004e6d3  mov     ecx, cs:dword_1800A453C
0x18004e6d9  mov     dword ptr [rbp+57h+var_A0], edi
0x18004e6dc  mov     dword ptr [rbp+57h+var_A0+4], 10100002h
0x18004e6e3  call    BfspGetBcdCopyFlags
0x18004e6e8  mov     rcx, [rbp+57h+var_80]
0x18004e6ec  lea     rdx, [rbp+57h+var_A0]
0x18004e6f0  mov     r8d, eax
0x18004e6f3  mov     r9, r15
0x18004e6f6  call    cs:__imp_BcdCopyObjects
0x18004e6fc  mov     ebx, eax
0x18004e6fe  test    eax, eax
0x18004e700  jns     short loc_18004E70E
0x18004e702  lea     rdx, aFailedToCopyBo; "Failed to copy bootmgr object data. Sta"...
0x18004e709  jmp     loc_18004E9F7
0x18004e70e  lea     r8, [rbp+57h+var_C8]
0x18004e712  mov     rcx, r15
0x18004e715  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18004e71c  call    cs:__imp_BcdOpenObject
0x18004e722  mov     ebx, eax
0x18004e724  test    eax, eax
0x18004e726  jns     short loc_18004E734
0x18004e728  lea     rdx, aFailedToOpenAH; "Failed to open a handle to the bootmgr "...
0x18004e72f  jmp     loc_18004E9F7
0x18004e734  cmp     [rbp+57h+var_D0], 0
0x18004e738  lea     rbx, [rbp+57h+var_60]
0x18004e73c  cmovz   rbx, [rbp+57h+Guid]
0x18004e741  test    rbx, rbx
0x18004e744  jz      short loc_18004E79C
0x18004e746  lea     rdx, [rbp+57h+DestinationString]; GuidString
0x18004e74a  mov     rcx, rbx; Guid
0x18004e74d  call    cs:__imp_RtlStringFromGUID
0x18004e753  lea     r8, [rbp+57h+DestinationString]
0x18004e757  mov     ecx, 2
0x18004e75c  lea     rdx, aSettingDefault; "Setting {default} to %wZ"
0x18004e763  call    BfspLogMessage
0x18004e768  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x18004e76c  call    cs:__imp_RtlFreeUnicodeString
0x18004e772  mov     rcx, [rbp+57h+var_C8]
0x18004e776  mov     r9d, 10h
0x18004e77c  mov     r8, rbx
0x18004e77f  mov     edx, 23000003h
0x18004e784  call    cs:__imp_BcdSetElementData
0x18004e78a  mov     ebx, eax
0x18004e78c  test    eax, eax
0x18004e78e  jns     short loc_18004E7B7
0x18004e790  lea     rdx, aFailedToSetDef; "Failed to set default bootmgr object. S"...
0x18004e797  jmp     loc_18004E9F7
0x18004e79c  test    cs:dword_1800A453C, 100h
0x18004e7a6  jz      short loc_18004E7B7
0x18004e7a8  mov     rcx, [rbp+57h+var_C8]
0x18004e7ac  mov     edx, 23000003h
0x18004e7b1  call    cs:__imp_BcdDeleteElement
0x18004e7b7  mov     rax, [rbp+57h+var_68]
0x18004e7bb  test    rax, rax
0x18004e7be  jz      short loc_18004E7F6
0x18004e7c0  test    cs:dword_1800A453C, 400h
0x18004e7ca  jz      short loc_18004E7F6
0x18004e7cc  mov     rcx, [rbp+57h+var_C8]
0x18004e7d0  mov     r9d, 10h
0x18004e7d6  mov     r8, rax
0x18004e7d9  mov     edx, 23000006h
0x18004e7de  call    cs:__imp_BcdSetElementData
0x18004e7e4  mov     ebx, eax
0x18004e7e6  test    eax, eax
0x18004e7e8  jns     short loc_18004E7F6
0x18004e7ea  lea     rdx, aFailedToSetBoo_1; "Failed to set bootmgr resume object. St"...
0x18004e7f1  jmp     loc_18004E9F7
0x18004e7f6  test    r14, r14
0x18004e7f9  jz      short loc_18004E822
0x18004e7fb  mov     rcx, [rbp+57h+var_C8]
0x18004e7ff  mov     r9d, r13d
0x18004e802  mov     r8, r14
0x18004e805  mov     edx, 24000001h
0x18004e80a  call    cs:__imp_BcdSetElementData
0x18004e810  mov     ebx, eax
0x18004e812  test    eax, eax
0x18004e814  jns     short loc_18004E822
0x18004e816  lea     rdx, aFailedToSetBoo_2; "Failed to set bootmgr display order. St"...
0x18004e81d  jmp     loc_18004E9F7
0x18004e822  test    rsi, rsi
0x18004e825  jz      short loc_18004E84E
0x18004e827  mov     rcx, [rbp+57h+var_C8]
0x18004e82b  mov     r9d, r12d
0x18004e82e  mov     r8, rsi
0x18004e831  mov     edx, 24000010h
0x18004e836  call    cs:__imp_BcdSetElementData
0x18004e83c  mov     ebx, eax
0x18004e83e  test    eax, eax
0x18004e840  jns     short loc_18004E84E
0x18004e842  lea     rdx, aFailedToSetBoo_0; "Failed to set bootmgr tools display ord"...
0x18004e849  jmp     loc_18004E9F7
0x18004e84e  mov     rax, [rbp+57h+Guid]
0x18004e852  test    rax, rax
0x18004e855  jz      short loc_18004E87D
0x18004e857  mov     rcx, [rbp+57h+var_C8]
0x18004e85b  xor     r9d, r9d
0x18004e85e  mov     r8, rax
0x18004e861  mov     edx, 24000001h
0x18004e866  call    BfspInsertObjectInDisplayOrder
0x18004e86b  mov     ebx, eax
0x18004e86d  test    eax, eax
0x18004e86f  jns     short loc_18004E87D
0x18004e871  lea     rdx, aFailedToUpdate; "Failed to update bootmgr display order."...
0x18004e878  jmp     loc_18004E9F7
0x18004e87d  mov     r13d, 2
0x18004e883  test    byte ptr cs:dword_1800A453C, r13b
0x18004e88a  jz      short loc_18004E8AE
0x18004e88c  mov     rcx, [rbp+57h+var_C8]
0x18004e890  lea     r8, GUID_WINDOWS_LEGACY_NTLDR
0x18004e897  xor     r9d, r9d
0x18004e89a  mov     edx, 24000001h
0x18004e89f  call    BfspInsertObjectInDisplayOrder
0x18004e8a4  mov     ebx, eax
0x18004e8a6  test    eax, eax
0x18004e8a8  js      loc_18004EA04
0x18004e8ae  test    cs:dword_1800A453C, 800h
0x18004e8b8  jz      short loc_18004E8DC
0x18004e8ba  mov     rcx, [rbp+57h+var_C8]
0x18004e8be  lea     r8, GUID_WINDOWS_MEMORY_TESTER
0x18004e8c5  xor     r9d, r9d
0x18004e8c8  mov     edx, 24000010h
0x18004e8cd  call    BfspInsertObjectInDisplayOrder
0x18004e8d2  mov     ebx, eax
0x18004e8d4  test    eax, eax
0x18004e8d6  js      loc_18004EA04
0x18004e8dc  mov     rcx, [rbp+57h+var_80]
0x18004e8e0  lea     r12, GUID_WINDOWS_BOOTMGR
0x18004e8e7  mov     r9, r12
0x18004e8ea  mov     r8, r12
0x18004e8ed  mov     rdx, r15
0x18004e8f0  call    BfspSetObjectDeviceAndPath
0x18004e8f5  mov     ebx, eax
0x18004e8f7  test    eax, eax
0x18004e8f9  js      loc_18004EA04
0x18004e8ff  cmp     cs:byte_1800A4538, 0
0x18004e906  jnz     short loc_18004E91C
0x18004e908  mov     rcx, [rbp+57h+var_C8]
0x18004e90c  mov     edx, 12000002h
0x18004e911  call    cs:__imp_BcdDeleteElement
0x18004e917  jmp     loc_18004E9DF
0x18004e91c  mov     ecx, cs:dword_1800A453C
0x18004e922  mov     edx, 220000h
0x18004e927  mov     eax, ecx
0x18004e929  and     eax, edx
0x18004e92b  cmp     eax, edx
0x18004e92d  jnz     short loc_18004E970
0x18004e92f  lea     rdx, aSettingNofirmw; "Setting \"nofirmwaresync\" element for "...
0x18004e936  mov     ecx, r13d
0x18004e939  call    BfspLogMessage
0x18004e93e  mov     rcx, [rbp+57h+var_C8]
0x18004e942  lea     r8, [rbp+57h+var_C0]
0x18004e946  mov     r9d, r13d
0x18004e949  mov     byte ptr [rbp+57h+var_C0], dil
0x18004e94d  mov     edx, 16000082h
0x18004e952  call    cs:__imp_BcdSetElementData
0x18004e958  mov     ebx, eax
0x18004e95a  test    eax, eax
0x18004e95c  jns     short loc_18004E96A
0x18004e95e  lea     rdx, aFailedToSetNof; "Failed to set \"nofirmwaresync\" elemen"...
0x18004e965  jmp     loc_18004E9F7
0x18004e96a  mov     ecx, cs:dword_1800A453C
0x18004e970  test    cl, 10h
0x18004e973  jnz     short loc_18004E9C6
0x18004e975  lea     r8, [rbp+57h+var_98]
0x18004e979  mov     rcx, r15
0x18004e97c  lea     rdx, GUID_FIRMWARE_BOOTMGR
0x18004e983  call    cs:__imp_BcdOpenObject
0x18004e989  mov     ebx, eax
0x18004e98b  test    eax, eax
0x18004e98d  jns     short loc_18004E998
0x18004e98f  lea     rdx, aFailedToOpenHa_2; "Failed to open handle to fwbootmgr obje"...
0x18004e996  jmp     short loc_18004E9F7
0x18004e998  mov     eax, cs:dword_1800A453C
0x18004e99e  test    al, al
0x18004e9a0  js      short loc_18004E9AA
0x18004e9a2  mov     edi, eax
0x18004e9a4  shr     edi, 0Bh
0x18004e9a7  and     edi, r13d
0x18004e9aa  mov     rcx, [rbp+57h+var_98]
0x18004e9ae  mov     r9d, edi
0x18004e9b1  mov     r8, r12
0x18004e9b4  mov     edx, 24000001h
0x18004e9b9  call    BfspInsertObjectInDisplayOrder
0x18004e9be  mov     ebx, eax
0x18004e9c0  test    eax, eax
0x18004e9c2  js      short loc_18004EA04
0x18004e9c4  jmp     short loc_18004E9DF
0x18004e9c6  test    ecx, 1080h
0x18004e9cc  jz      short loc_18004E9DF
0x18004e9ce  lea     rdx, aAddbootmgrlast; "AddBootmgrLast and PreserveBootOrder op"...
0x18004e9d5  mov     ecx, 4
0x18004e9da  call    BfspLogMessage
0x18004e9df  mov     rdx, r12
0x18004e9e2  mov     rcx, r15
0x18004e9e5  call    BfspSetLocale
  ... truncated ...
```
