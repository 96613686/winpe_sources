# BfspCreateBootmgrObject

- ea: `0x1400052bc`
- end: `0x140005835`
- name: `BfspCreateBootmgrObject`
- size: `1401`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, GUID *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140005e18`
- `0x140007cdc`

## callees

- `0x1400052bc`
- `0x1400069e0`
- `0x140006a14`
- `0x1400074f4`
- `0x1400087a8`
- `0x140008844`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x140014ec8`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x140026650`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400057da`
- `KERNEL32!HeapFree` at `0x1400057f3`
- `KERNEL32!HeapFree` at `0x1400057da`
- `KERNEL32!HeapFree` at `0x1400057f3`
- `KERNEL32!GetProcessHeap` at `0x1400057cc`
- `KERNEL32!GetProcessHeap` at `0x1400057e5`
- `KERNEL32!GetProcessHeap` at `0x1400057cc`
- `KERNEL32!GetProcessHeap` at `0x1400057e5`
- `ntdll!RtlStringFromGUID` at `0x1400054e5`
- `ntdll!RtlStringFromGUID` at `0x1400054e5`
- `ntdll!RtlFreeUnicodeString` at `0x140005504`
- `ntdll!RtlFreeUnicodeString` at `0x140005504`
- `ntdll!RtlInitUnicodeString` at `0x140005338`
- `ntdll!RtlInitUnicodeString` at `0x140005338`

## string_xrefs

- `0x140005344`: `Create BOOTMGR object RetainBootDefault:%c`
- `0x140005486`: `Failed to copy bootmgr object data. Status = [%x]`
- `0x1400054ae`: `Failed to open a handle to the bootmgr object. Status = [%x]`
- `0x140005619`: `Failed to update bootmgr display order. Status = [%x]`
- `0x140005739`: `Failed to open handle to fwbootmgr object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateBootmgrObject(__int64 a1, __int64 a2, __int64 a3, GUID *a4)
{
  void *v5; // r15
  void *v6; // r12
  void *v7; // r14
  int v8; // eax
  HANDLE v9; // rdi
  unsigned int v10; // esi
  int BcdElementData; // eax
  int v12; // ebx
  int v13; // eax
  __int64 v14; // r8
  unsigned int BcdCopyFlags; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // r8
  GUID *v19; // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int inserted; // eax
  __int64 v25; // r8
  __int16 v26; // cx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v31; // rax
  char v33; // [rsp+30h] [rbp-79h]
  __int16 v34; // [rsp+34h] [rbp-75h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v36; // [rsp+3Ch] [rbp-6Dh]
  unsigned int v37; // [rsp+40h] [rbp-69h]
  HANDLE v38; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-51h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-49h] BYREF
  LPVOID v42; // [rsp+68h] [rbp-41h] BYREF
  void *v43; // [rsp+70h] [rbp-39h] BYREF
  GUID *Guid; // [rsp+78h] [rbp-31h]
  __int64 v45; // [rsp+80h] [rbp-29h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-21h] BYREF
  __int64 v47; // [rsp+98h] [rbp-11h]
  __int128 v48; // [rsp+A0h] [rbp-9h] BYREF

  v45 = a1;
  v34 = 0;
  Handle = 0;
  v38 = 0;
  v42 = 0;
  v36 = 0;
  v48 = 0;
  v5 = 0;
  v39 = 0;
  DestinationString = 0;
  v6 = 0;
  v43 = 0;
  v33 = 0;
  v7 = 0;
  lpMem = 0;
  v37 = 0;
  v35 = 0;
  Guid = a4;
  v47 = a3;
  RtlInitUnicodeString(&DestinationString, 0);
  BfspLogMessage(2, L"Create BOOTMGR object RetainBootDefault:%c", (dword_14003F8FC & 0x100) != 0 ? 121 : 110);
  v8 = BcdOpenObject(a2, &GUID_WINDOWS_BOOTMGR, &v38);
  v9 = v38;
  v10 = 1;
  if ( v8 >= 0 )
  {
    BcdElementData = BfspGetBcdElementData(v38, 603979777, &v42, &v39);
    v12 = BcdElementData;
    if ( BcdElementData == -1073741275 )
    {
      v36 = 0;
    }
    else
    {
      v5 = v42;
      if ( BcdElementData < 0 )
        goto LABEL_63;
      v36 = v39;
    }
    v13 = BfspGetBcdElementData(v9, 603979792, &lpMem, &v35);
    v12 = v13;
    if ( v13 == -1073741275 )
    {
      v7 = 0;
      v37 = 0;
    }
    else
    {
      v7 = lpMem;
      if ( v13 < 0 )
        goto LABEL_61;
      v37 = v35;
    }
    if ( (dword_14003F8FC & 0x100) != 0 )
    {
      v35 = 16;
      if ( (int)BcdGetElementDataWithFlags((__int64)v9, 0x23000003u, v14, (__int64)&v48, &v35) >= 0
        && (int)BcdOpenObject(a2, &v48, &Handle) >= 0 )
      {
        v33 = 1;
        BcdCloseObject(Handle);
      }
    }
    BcdCloseObject(v9);
    v9 = 0;
    v38 = 0;
  }
  Handle = HANDLE_FLAG_INHERIT;
  BcdCopyFlags = BfspGetBcdCopyFlags((unsigned int)dword_14003F8FC);
  v16 = BcdCopyObjects(v45, (unsigned int *)&Handle, BcdCopyFlags, a2);
  v12 = v16;
  if ( v16 < 0 )
  {
    BfspLogMessage(4, L"Failed to copy bootmgr object data. Status = [%x]", (unsigned int)v16);
    goto LABEL_61;
  }
  v17 = BcdOpenObject(a2, &GUID_WINDOWS_BOOTMGR, &v38);
  v12 = v17;
  if ( v17 < 0 )
  {
    BfspLogMessage(4, L"Failed to open a handle to the bootmgr object. Status = [%x]", (unsigned int)v17);
    v9 = v38;
    goto LABEL_61;
  }
  v19 = (GUID *)&v48;
  v9 = v38;
  if ( !v33 )
    v19 = Guid;
  if ( v19 )
  {
    RtlStringFromGUID(v19, &DestinationString);
    BfspLogMessage(2, L"Setting {default} to %wZ", &DestinationString);
    RtlFreeUnicodeString(&DestinationString);
    v20 = BcdSetElementDataWithFlags((__int64)v9, 587202563, 0, (__int64)v19, 0x10u);
    v12 = v20;
    if ( v20 < 0 )
    {
      BfspLogMessage(4, L"Failed to set default bootmgr object. Status = [%x]", (unsigned int)v20);
      goto LABEL_61;
    }
  }
  else if ( (dword_14003F8FC & 0x100) != 0 )
  {
    LOBYTE(v18) = 1;
    BiDeleteElement(v38, 587202563, v18);
  }
  if ( v47 )
  {
    if ( (dword_14003F8FC & 0x400) != 0 )
    {
      v21 = BcdSetElementDataWithFlags((__int64)v9, 587202566, 0, v47, 0x10u);
      v12 = v21;
      if ( v21 < 0 )
      {
        BfspLogMessage(4, L"Failed to set bootmgr resume object. Status = [%x]", (unsigned int)v21);
        goto LABEL_61;
      }
    }
  }
  if ( v5 )
  {
    v22 = BcdSetElementDataWithFlags((__int64)v9, 603979777, 0, (__int64)v5, v36);
    v12 = v22;
    if ( v22 < 0 )
    {
      BfspLogMessage(4, L"Failed to set bootmgr display order. Status = [%x]", (unsigned int)v22);
      goto LABEL_61;
    }
  }
  if ( v7 )
  {
    v23 = BcdSetElementDataWithFlags((__int64)v9, 603979792, 0, (__int64)v7, v37);
    v12 = v23;
    if ( v23 < 0 )
    {
      BfspLogMessage(4, L"Failed to set bootmgr tools display order. Status = [%x]", (unsigned int)v23);
      goto LABEL_61;
    }
  }
  if ( Guid )
  {
    inserted = BfspInsertObjectInDisplayOrder(v9, 603979777, Guid, 0);
    v12 = inserted;
    if ( inserted < 0 )
    {
      BfspLogMessage(4, L"Failed to update bootmgr display order. Status = [%x]", (unsigned int)inserted);
      goto LABEL_61;
    }
  }
  if ( (dword_14003F8FC & 2) == 0
    || (v12 = BfspInsertObjectInDisplayOrder(v9, 603979777, &GUID_WINDOWS_LEGACY_NTLDR, 0), v12 >= 0) )
  {
    if ( (dword_14003F8FC & 0x800) == 0
      || (v12 = BfspInsertObjectInDisplayOrder(v9, 603979792, &GUID_WINDOWS_MEMORY_TESTER, 0), v12 >= 0) )
    {
      v12 = BfspSetObjectDeviceAndPath(v45, a2, &GUID_WINDOWS_BOOTMGR, &GUID_WINDOWS_BOOTMGR);
      if ( v12 >= 0 )
      {
        if ( !byte_14003F8F8 )
        {
          LOBYTE(v25) = 1;
          BiDeleteElement(v9, 301989890, v25);
LABEL_59:
          v29 = BfspSetLocale(a2, &GUID_WINDOWS_BOOTMGR);
          v12 = v29;
          if ( v29 < 0 )
            BfspLogMessage(4, L"Failed to set {bootmgr} locale. Status = [%x]", (unsigned int)v29);
          goto LABEL_61;
        }
        v26 = dword_14003F8FC;
        if ( (dword_14003F8FC & 0x220000) == 0x220000 )
        {
          BfspLogMessage(2, L"Setting \"nofirmwaresync\" element for {bootmgr} object");
          LOBYTE(v34) = 1;
          v27 = BcdSetElementDataWithFlags((__int64)v9, 369098882, 0, (__int64)&v34, 2u);
          v12 = v27;
          if ( v27 < 0 )
          {
            BfspLogMessage(
              4,
              L"Failed to set \"nofirmwaresync\" element for {bootmgr} object. Status = [%x]",
              (unsigned int)v27);
            goto LABEL_61;
          }
          v26 = dword_14003F8FC;
        }
        if ( (v26 & 0x10) != 0 )
        {
          if ( (v26 & 0x1080) != 0 )
            BfspLogMessage(
              4,
              L"AddBootmgrLast and PreserveBootOrder options are ignored when custom volume is specified");
          goto LABEL_59;
        }
        v28 = BcdOpenObject(a2, &GUID_FIRMWARE_BOOTMGR, &v43);
        v12 = v28;
        if ( v28 >= 0 )
        {
          if ( (dword_14003F8FC & 0x80u) == 0 )
            v10 = ((unsigned int)dword_14003F8FC >> 11) & 2;
          v6 = v43;
          v12 = BfspInsertObjectInDisplayOrder(v43, 603979777, &GUID_WINDOWS_BOOTMGR, v10);
          if ( v12 < 0 )
            goto LABEL_61;
          goto LABEL_59;
        }
        BfspLogMessage(4, L"Failed to open handle to fwbootmgr object. Status = [%x]", (unsigned int)v28);
        v6 = v43;
      }
    }
  }
LABEL_61:
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
LABEL_63:
  if ( v5 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v5);
  }
  if ( v9 )
    BcdCloseObject(v9);
  if ( v6 )
    BcdCloseObject(v6);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400052bc  push    rbp
0x1400052be  push    rbx
0x1400052bf  push    rsi
0x1400052c0  push    rdi
0x1400052c1  push    r12
0x1400052c3  push    r13
0x1400052c5  push    r14
0x1400052c7  push    r15
0x1400052c9  lea     rbp, [rsp-1Fh]
0x1400052ce  sub     rsp, 0C8h
0x1400052d5  mov     rax, cs:__security_cookie
0x1400052dc  xor     rax, rsp
0x1400052df  mov     [rbp+57h+var_50], rax
0x1400052e3  xor     ebx, ebx
0x1400052e5  mov     [rbp+57h+var_80], rcx
0x1400052e9  mov     r13, rdx
0x1400052ec  mov     [rbp+57h+var_CC], bx
0x1400052f0  xorps   xmm0, xmm0
0x1400052f3  mov     [rbp+57h+Handle], rbx
0x1400052f7  xorps   xmm1, xmm1
0x1400052fa  mov     [rbp+57h+var_B8], rbx
0x1400052fe  xor     edx, edx; SourceString
0x140005300  mov     [rbp+57h+var_98], rbx
0x140005304  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005308  mov     [rbp+57h+var_C4], ebx
0x14000530b  movups  [rbp+57h+var_60], xmm0
0x14000530f  mov     r15d, ebx
0x140005312  mov     [rbp+57h+var_B0], ebx
0x140005315  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140005319  mov     r12d, ebx
0x14000531c  mov     [rbp+57h+var_90], rbx
0x140005320  mov     [rbp+57h+var_D0], bl
0x140005323  mov     r14d, ebx
0x140005326  mov     [rbp+57h+lpMem], rbx
0x14000532a  mov     [rbp+57h+var_C0], ebx
0x14000532d  mov     [rbp+57h+var_C8], ebx
0x140005330  mov     [rbp+57h+Guid], r9
0x140005334  mov     [rbp+57h+var_68], r8
0x140005338  call    cs:__imp_RtlInitUnicodeString
0x14000533e  mov     eax, cs:dword_14003F8FC
0x140005344  lea     rdx, aCreateBootmgrO; "Create BOOTMGR object RetainBootDefault"...
0x14000534b  and     eax, 100h
0x140005350  lea     ecx, [rbx+2]
0x140005353  neg     eax
0x140005355  sbb     r8d, r8d
0x140005358  and     r8d, 0Bh
0x14000535c  add     r8d, 6Eh ; 'n'
0x140005360  call    BfspLogMessage
0x140005365  lea     r8, [rbp+57h+var_B8]
0x140005369  mov     rcx, r13
0x14000536c  lea     rdx, GUID_WINDOWS_BOOTMGR
0x140005373  call    BcdOpenObject
0x140005378  mov     rdi, [rbp+57h+var_B8]
0x14000537c  lea     esi, [rbx+1]
0x14000537f  test    eax, eax
0x140005381  js      loc_140005458
0x140005387  lea     r9, [rbp+57h+var_B0]
0x14000538b  mov     edx, 24000001h
0x140005390  lea     r8, [rbp+57h+var_98]
0x140005394  mov     rcx, rdi
0x140005397  call    BfspGetBcdElementData
0x14000539c  mov     r14d, 0C0000225h
0x1400053a2  mov     ebx, eax
0x1400053a4  cmp     eax, r14d
0x1400053a7  jnz     short loc_1400053AF
0x1400053a9  mov     [rbp+57h+var_C4], r12d
0x1400053ad  jmp     short loc_1400053C1
0x1400053af  mov     r15, [rbp+57h+var_98]
0x1400053b3  test    eax, eax
0x1400053b5  js      loc_1400057E0
0x1400053bb  mov     eax, [rbp+57h+var_B0]
0x1400053be  mov     [rbp+57h+var_C4], eax
0x1400053c1  lea     r9, [rbp+57h+var_C8]
0x1400053c5  mov     edx, 24000010h
0x1400053ca  lea     r8, [rbp+57h+lpMem]
0x1400053ce  mov     rcx, rdi
0x1400053d1  call    BfspGetBcdElementData
0x1400053d6  mov     ebx, eax
0x1400053d8  cmp     eax, r14d
0x1400053db  jnz     short loc_1400053E6
0x1400053dd  xor     r14d, r14d
0x1400053e0  mov     [rbp+57h+var_C0], r12d
0x1400053e4  jmp     short loc_1400053F8
0x1400053e6  mov     r14, [rbp+57h+lpMem]
0x1400053ea  test    eax, eax
0x1400053ec  js      loc_1400057C7
0x1400053f2  mov     eax, [rbp+57h+var_C8]
0x1400053f5  mov     [rbp+57h+var_C0], eax
0x1400053f8  test    cs:dword_14003F8FC, 100h
0x140005402  jz      short loc_14000544A
0x140005404  lea     rax, [rbp+57h+var_C8]
0x140005408  mov     [rbp+57h+var_C8], 10h
0x14000540f  lea     r9, [rbp+57h+var_60]
0x140005413  mov     [rsp+100h+var_E0], rax
0x140005418  mov     edx, 23000003h
0x14000541d  mov     rcx, rdi
0x140005420  call    BcdGetElementDataWithFlags
0x140005425  test    eax, eax
0x140005427  js      short loc_14000544A
0x140005429  lea     r8, [rbp+57h+Handle]
0x14000542d  mov     rcx, r13
0x140005430  lea     rdx, [rbp+57h+var_60]
0x140005434  call    BcdOpenObject
0x140005439  test    eax, eax
0x14000543b  js      short loc_14000544A
0x14000543d  mov     rcx, [rbp+57h+Handle]; Handle
0x140005441  mov     [rbp+57h+var_D0], sil
0x140005445  call    BcdCloseObject
0x14000544a  mov     rcx, rdi; Handle
0x14000544d  call    BcdCloseObject
0x140005452  xor     edi, edi
0x140005454  mov     [rbp+57h+var_B8], rdi
0x140005458  mov     ecx, cs:dword_14003F8FC
0x14000545e  mov     dword ptr [rbp+57h+Handle], esi
0x140005461  mov     dword ptr [rbp+57h+Handle+4], 10100002h
0x140005468  call    BfspGetBcdCopyFlags
0x14000546d  mov     rcx, [rbp+57h+var_80]
0x140005471  lea     rdx, [rbp+57h+Handle]
0x140005475  mov     r8d, eax
0x140005478  mov     r9, r13
0x14000547b  call    BcdCopyObjects
0x140005480  mov     ebx, eax
0x140005482  test    eax, eax
0x140005484  jns     short loc_140005492
0x140005486  lea     rdx, aFailedToCopyBo; "Failed to copy bootmgr object data. Sta"...
0x14000548d  jmp     loc_1400057BA
0x140005492  lea     r8, [rbp+57h+var_B8]
0x140005496  mov     rcx, r13
0x140005499  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1400054a0  call    BcdOpenObject
0x1400054a5  mov     ebx, eax
0x1400054a7  test    eax, eax
0x1400054a9  jns     short loc_1400054C8
0x1400054ab  mov     r8d, eax
0x1400054ae  lea     rdx, aFailedToOpenAH; "Failed to open a handle to the bootmgr "...
0x1400054b5  mov     ecx, 4
0x1400054ba  call    BfspLogMessage
0x1400054bf  mov     rdi, [rbp+57h+var_B8]
0x1400054c3  jmp     loc_1400057C7
0x1400054c8  cmp     [rbp+57h+var_D0], r12b
0x1400054cc  lea     rbx, [rbp+57h+var_60]
0x1400054d0  mov     rdi, [rbp+57h+var_B8]
0x1400054d4  cmovz   rbx, [rbp+57h+Guid]
0x1400054d9  test    rbx, rbx
0x1400054dc  jz      short loc_140005537
0x1400054de  lea     rdx, [rbp+57h+DestinationString]; GuidString
0x1400054e2  mov     rcx, rbx; Guid
0x1400054e5  call    cs:__imp_RtlStringFromGUID
0x1400054eb  lea     r8, [rbp+57h+DestinationString]
0x1400054ef  mov     ecx, 2
0x1400054f4  lea     rdx, aSettingDefault; "Setting {default} to %wZ"
0x1400054fb  call    BfspLogMessage
0x140005500  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x140005504  call    cs:__imp_RtlFreeUnicodeString
0x14000550a  mov     r9, rbx
0x14000550d  mov     dword ptr [rsp+100h+var_E0], 10h
0x140005515  xor     r8d, r8d
0x140005518  mov     edx, 23000003h
0x14000551d  mov     rcx, rdi
0x140005520  call    BcdSetElementDataWithFlags
0x140005525  mov     ebx, eax
0x140005527  test    eax, eax
0x140005529  jns     short loc_140005553
0x14000552b  lea     rdx, aFailedToSetDef; "Failed to set default bootmgr object. S"...
0x140005532  jmp     loc_1400057BA
0x140005537  test    cs:dword_14003F8FC, 100h
0x140005541  jz      short loc_140005553
0x140005543  mov     r8b, sil
0x140005546  mov     edx, 23000003h
0x14000554b  mov     rcx, rdi
0x14000554e  call    BiDeleteElement
0x140005553  mov     rax, [rbp+57h+var_68]
0x140005557  test    rax, rax
0x14000555a  jz      short loc_140005595
0x14000555c  test    cs:dword_14003F8FC, 400h
0x140005566  jz      short loc_140005595
0x140005568  mov     r9, rax
0x14000556b  mov     dword ptr [rsp+100h+var_E0], 10h
0x140005573  xor     r8d, r8d
0x140005576  mov     edx, 23000006h
0x14000557b  mov     rcx, rdi
0x14000557e  call    BcdSetElementDataWithFlags
0x140005583  mov     ebx, eax
0x140005585  test    eax, eax
0x140005587  jns     short loc_140005595
0x140005589  lea     rdx, aFailedToSetBoo_3; "Failed to set bootmgr resume object. St"...
0x140005590  jmp     loc_1400057BA
0x140005595  test    r15, r15
0x140005598  jz      short loc_1400055C6
0x14000559a  mov     eax, [rbp+57h+var_C4]
0x14000559d  mov     r9, r15
0x1400055a0  xor     r8d, r8d
0x1400055a3  mov     dword ptr [rsp+100h+var_E0], eax
0x1400055a7  mov     edx, 24000001h
0x1400055ac  mov     rcx, rdi
0x1400055af  call    BcdSetElementDataWithFlags
0x1400055b4  mov     ebx, eax
0x1400055b6  test    eax, eax
0x1400055b8  jns     short loc_1400055C6
0x1400055ba  lea     rdx, aFailedToSetBoo_4; "Failed to set bootmgr display order. St"...
0x1400055c1  jmp     loc_1400057BA
0x1400055c6  test    r14, r14
0x1400055c9  jz      short loc_1400055F7
0x1400055cb  mov     eax, [rbp+57h+var_C0]
0x1400055ce  mov     r9, r14
0x1400055d1  xor     r8d, r8d
0x1400055d4  mov     dword ptr [rsp+100h+var_E0], eax
0x1400055d8  mov     edx, 24000010h
0x1400055dd  mov     rcx, rdi
0x1400055e0  call    BcdSetElementDataWithFlags
0x1400055e5  mov     ebx, eax
0x1400055e7  test    eax, eax
0x1400055e9  jns     short loc_1400055F7
0x1400055eb  lea     rdx, aFailedToSetBoo_2; "Failed to set bootmgr tools display ord"...
0x1400055f2  jmp     loc_1400057BA
0x1400055f7  mov     rax, [rbp+57h+Guid]
0x1400055fb  test    rax, rax
0x1400055fe  jz      short loc_140005625
0x140005600  xor     r9d, r9d
0x140005603  mov     r8, rax
0x140005606  mov     edx, 24000001h
0x14000560b  mov     rcx, rdi
0x14000560e  call    BfspInsertObjectInDisplayOrder
0x140005613  mov     ebx, eax
0x140005615  test    eax, eax
0x140005617  jns     short loc_140005625
0x140005619  lea     rdx, aFailedToUpdate; "Failed to update bootmgr display order."...
0x140005620  jmp     loc_1400057BA
0x140005625  test    byte ptr cs:dword_14003F8FC, 2
0x14000562c  jz      short loc_14000564F
0x14000562e  xor     r9d, r9d
0x140005631  lea     r8, GUID_WINDOWS_LEGACY_NTLDR
0x140005638  mov     edx, 24000001h
0x14000563d  mov     rcx, rdi
0x140005640  call    BfspInsertObjectInDisplayOrder
0x140005645  mov     ebx, eax
0x140005647  test    eax, eax
0x140005649  js      loc_1400057C7
0x14000564f  test    cs:dword_14003F8FC, 800h
0x140005659  jz      short loc_14000567C
0x14000565b  xor     r9d, r9d
0x14000565e  lea     r8, GUID_WINDOWS_MEMORY_TESTER
0x140005665  mov     edx, 24000010h
0x14000566a  mov     rcx, rdi
0x14000566d  call    BfspInsertObjectInDisplayOrder
0x140005672  mov     ebx, eax
0x140005674  test    eax, eax
0x140005676  js      loc_1400057C7
0x14000567c  mov     rcx, [rbp+57h+var_80]
0x140005680  lea     r9, GUID_WINDOWS_BOOTMGR
0x140005687  lea     r8, GUID_WINDOWS_BOOTMGR
0x14000568e  mov     rdx, r13
0x140005691  call    BfspSetObjectDeviceAndPath
0x140005696  mov     ebx, eax
0x140005698  test    eax, eax
0x14000569a  js      loc_1400057C7
0x1400056a0  cmp     cs:byte_14003F8F8, r12b
0x1400056a7  jnz     short loc_1400056BE
0x1400056a9  mov     r8b, sil
0x1400056ac  mov     edx, 12000002h
0x1400056b1  mov     rcx, rdi
0x1400056b4  call    BiDeleteElement
0x1400056b9  jmp     loc_14000579E
0x1400056be  mov     ecx, cs:dword_14003F8FC
0x1400056c4  mov     edx, 220000h
0x1400056c9  mov     eax, ecx
0x1400056cb  and     eax, edx
0x1400056cd  cmp     eax, edx
0x1400056cf  jnz     short loc_140005718
0x1400056d1  mov     ebx, 2
0x1400056d6  lea     rdx, aSettingNofirmw; "Setting \"nofirmwaresync\" element for "...
0x1400056dd  mov     ecx, ebx
0x1400056df  call    BfspLogMessage
0x1400056e4  lea     r9, [rbp+57h+var_CC]
0x1400056e8  mov     byte ptr [rbp+57h+var_CC], sil
0x1400056ec  xor     r8d, r8d
0x1400056ef  mov     dword ptr [rsp+100h+var_E0], ebx
0x1400056f3  mov     edx, 16000082h
0x1400056f8  mov     rcx, rdi
0x1400056fb  call    BcdSetElementDataWithFlags
0x140005700  mov     ebx, eax
0x140005702  test    eax, eax
0x140005704  jns     short loc_140005712
0x140005706  lea     rdx, aFailedToSetNof; "Failed to set \"nofirmwaresync\" elemen"...
0x14000570d  jmp     loc_1400057BA
0x140005712  mov     ecx, cs:dword_14003F8FC
0x140005718  test    cl, 10h
0x14000571b  jnz     short loc_140005785
0x14000571d  lea     r8, [rbp+57h+var_90]
0x140005721  mov     rcx, r13
0x140005724  lea     rdx, GUID_FIRMWARE_BOOTMGR
0x14000572b  call    BcdOpenObject
0x140005730  mov     ebx, eax
0x140005732  test    eax, eax
0x140005734  jns     short loc_140005750
0x140005736  mov     r8d, eax
0x140005739  lea     rdx, aFailedToOpenHa_2; "Failed to open handle to fwbootmgr obje"...
0x140005740  mov     ecx, 4
0x140005745  call    BfspLogMessage
0x14000574a  mov     r12, [rbp+57h+var_90]
  ... truncated ...
```
