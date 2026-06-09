# BfspRemoveDuplicateEntries

- ea: `0x180050554`
- end: `0x1800507f6`
- name: `BfspRemoveDuplicateEntries`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180050410`

## callees

- `0x18004cdd4`
- `0x18004e384`
- `0x18004f454`
- `0x18004f774`
- `0x1800502fc`
- `0x180050554`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x1800506e8`
- `ntdll!RtlStringFromGUID` at `0x1800506e8`
- `ntdll!RtlFreeUnicodeString` at `0x180050707`
- `ntdll!RtlFreeUnicodeString` at `0x180050707`
- `ntdll!RtlInitUnicodeString` at `0x1800505ad`
- `ntdll!RtlInitUnicodeString` at `0x1800505ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800507ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800507ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800507a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800507a0`
- `bcd!BcdCloseObject` at `0x1800506ce`
- `bcd!BcdCloseObject` at `0x180050753`
- `bcd!BcdCloseObject` at `0x180050795`
- `bcd!BcdCloseObject` at `0x1800507bd`
- `bcd!BcdCloseObject` at `0x1800506ce`
- `bcd!BcdCloseObject` at `0x180050753`
- `bcd!BcdCloseObject` at `0x180050795`
- `bcd!BcdCloseObject` at `0x1800507bd`
- `bcd!BcdOpenObject` at `0x1800505de`
- `bcd!BcdOpenObject` at `0x180050669`
- `bcd!BcdOpenObject` at `0x180050737`
- `bcd!BcdOpenObject` at `0x1800505de`
- `bcd!BcdOpenObject` at `0x180050669`
- `bcd!BcdOpenObject` at `0x180050737`
- `bcd!BcdDeleteObject` at `0x180050711`
- `bcd!BcdDeleteObject` at `0x180050711`

## string_xrefs

- `0x1800505ea`: `Failed to open a handle to the OS loader element. Status = [%x]`
- `0x18005076c`: `Failed to remove duplicate object from bootmgr display order. Status = [%x]`
- `0x1800507de`: `Failed to delete duplicate loader object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspRemoveDuplicateEntries(__int64 a1, _QWORD *a2)
{
  char *v4; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // r14
  char *v10; // rsi
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  char v15; // r8
  char IsSetupObject; // al
  char v17; // r9
  char v18; // r8
  char v19; // cl
  int v20; // eax
  __int64 v21; // rdx
  int v22; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-30h] BYREF
  char *v27; // [rsp+48h] [rbp-28h] BYREF
  __int64 v28; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  char v30; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp+48h] BYREF

  v25 = 0;
  v26 = 0;
  v30 = 0;
  v4 = 0;
  v31 = 0;
  v27 = 0;
  v28 = 0;
  DestinationString = 0;
  v24 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( (dword_1800A453C & 4) == 0 )
    return 0;
  BfspLogMessage(2, L"Removing duplicate entries.");
  v6 = BcdOpenObject(a1, a2, &v28);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v25 = 0x1020000300000001LL;
    v8 = BfspEnumerateObjects(a1, &v25, &v31, &v27);
    v4 = v27;
    v7 = v8;
    if ( v8 < 0 )
      goto LABEL_26;
    v9 = 0;
    if ( !v31 )
    {
LABEL_25:
      v7 = 0;
      goto LABEL_26;
    }
    while ( 1 )
    {
      v10 = &v4[24 * v9];
      if ( *(_QWORD *)v10 != *a2 || *((_QWORD *)v10 + 1) != a2[1] )
      {
        v11 = BcdOpenObject(a1, &v4[24 * v9], &v24);
        v7 = v11;
        if ( v11 < 0 )
        {
          BfspLogMessage(4, L"Failed to get a handle to the OS loader. Status = [%x]", (unsigned int)v11);
          goto LABEL_26;
        }
        v14 = BfspCompareObjects(v28, v24, v12, v13, (__int64)&v30);
        v15 = v30;
        if ( v14 < 0 )
          v15 = 0;
        v30 = v15;
        if ( (dword_1800A453C & 1) == 0 )
        {
          IsSetupObject = BfspIsSetupObject(&v4[24 * v9]);
          v19 = v18;
          if ( IsSetupObject )
            v19 = v17;
          v15 = v19;
          v30 = v19;
        }
        if ( v15 )
        {
          RtlStringFromGUID((const GUID *const)&v4[24 * v9], &DestinationString);
          BfspLogMessage(2, L"Removing duplicate object %wZ", &DestinationString);
          RtlFreeUnicodeString(&DestinationString);
          v20 = BcdDeleteObject(v24);
          v24 = 0;
          v7 = v20;
          if ( v20 < 0 )
          {
            BfspLogMessage(4, L"Failed to delete duplicate loader object. Status = [%x]", (unsigned int)v20);
            goto LABEL_26;
          }
          if ( (int)BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v26) >= 0 )
          {
            v22 = BfspDeleteObjectFromDisplayOrder(v26, v21, &v4[24 * v9]);
            BcdCloseObject(v26);
            if ( v22 < 0 && !(unsigned __int8)BfspIsSetupObject(&v4[24 * v9]) )
              BfspLogMessage(
                3,
                L"Failed to remove duplicate object from bootmgr display order. Status = [%x]",
                (unsigned int)v22);
          }
        }
        else
        {
          BcdCloseObject(v24);
          v24 = 0;
        }
      }
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v31 )
        goto LABEL_25;
    }
  }
  BfspLogMessage(4, L"Failed to open a handle to the OS loader element. Status = [%x]", (unsigned int)v6);
LABEL_26:
  if ( v24 )
    BcdCloseObject(v24);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( v28 )
    BcdCloseObject(v28);
  return v7;
}

```

## disassembly

```asm
0x180050554  mov     [rsp-28h+arg_0], rbx
0x180050559  mov     [rsp-28h+arg_8], rsi
0x18005055e  push    rbp
0x18005055f  push    rdi
0x180050560  push    r13
0x180050562  push    r14
0x180050564  push    r15
0x180050566  mov     rbp, rsp
0x180050569  sub     rsp, 70h
0x18005056d  mov     r13, rdx
0x180050570  mov     [rbp+var_38], 0
0x180050578  mov     r15, rcx
0x18005057b  mov     [rbp+var_30], 0
0x180050583  xorps   xmm0, xmm0
0x180050586  mov     [rbp+arg_10], 0
0x18005058a  xor     edi, edi
0x18005058c  mov     [rbp+arg_18], 0
0x180050593  xor     edx, edx; SourceString
0x180050595  mov     [rbp+var_28], rdi
0x180050599  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005059d  mov     [rbp+var_20], rdi
0x1800505a1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800505a5  mov     [rbp+var_40], 0
0x1800505ad  call    cs:__imp_RtlInitUnicodeString
0x1800505b3  test    byte ptr cs:dword_1800A453C, 4
0x1800505ba  jnz     short loc_1800505C3
0x1800505bc  xor     eax, eax
0x1800505be  jmp     loc_1800507C5
0x1800505c3  lea     rdx, aRemovingDuplic_0; "Removing duplicate entries."
0x1800505ca  mov     ecx, 2
0x1800505cf  call    BfspLogMessage
0x1800505d4  lea     r8, [rbp+var_20]
0x1800505d8  mov     rdx, r13
0x1800505db  mov     rcx, r15
0x1800505de  call    cs:__imp_BcdOpenObject
0x1800505e4  mov     ebx, eax
0x1800505e6  test    eax, eax
0x1800505e8  jns     short loc_180050603
0x1800505ea  lea     rdx, aFailedToOpenAH_1; "Failed to open a handle to the OS loade"...
0x1800505f1  mov     r8d, eax
0x1800505f4  mov     ecx, 4
0x1800505f9  call    BfspLogMessage
0x1800505fe  jmp     loc_18005078C
0x180050603  lea     r9, [rbp+var_28]
0x180050607  mov     dword ptr [rbp+var_38], 1
0x18005060e  lea     r8, [rbp+arg_18]
0x180050612  mov     dword ptr [rbp+var_38+4], 10200003h
0x180050619  lea     rdx, [rbp+var_38]
0x18005061d  mov     rcx, r15
0x180050620  call    BfspEnumerateObjects
0x180050625  mov     rdi, [rbp+var_28]
0x180050629  mov     ebx, eax
0x18005062b  test    eax, eax
0x18005062d  js      loc_18005078C
0x180050633  xor     r14d, r14d
0x180050636  cmp     [rbp+arg_18], r14d
0x18005063a  jbe     loc_18005078A
0x180050640  lea     rcx, [r14+r14*2]
0x180050644  lea     rsi, [rdi+rcx*8]
0x180050648  mov     rax, [rsi]
0x18005064b  cmp     rax, [r13+0]
0x18005064f  jnz     short loc_18005065F
0x180050651  mov     rax, [rsi+8]
0x180050655  cmp     rax, [r13+8]
0x180050659  jz      loc_18005077D
0x18005065f  lea     r8, [rbp+var_40]
0x180050663  mov     rdx, rsi
0x180050666  mov     rcx, r15
0x180050669  call    cs:__imp_BcdOpenObject
0x18005066f  mov     ebx, eax
0x180050671  test    eax, eax
0x180050673  js      loc_1800507EA
0x180050679  mov     rdx, [rbp+var_40]
0x18005067d  lea     rax, [rbp+arg_10]
0x180050681  mov     rcx, [rbp+var_20]
0x180050685  mov     [rsp+70h+var_50], rax
0x18005068a  call    BfspCompareObjects
0x18005068f  movzx   r8d, [rbp+arg_10]
0x180050694  xor     ecx, ecx
0x180050696  test    eax, eax
0x180050698  cmovs   r8d, ecx
0x18005069c  lea     r9d, [rcx+1]
0x1800506a0  mov     [rbp+arg_10], r8b
0x1800506a4  test    byte ptr cs:dword_1800A453C, r9b
0x1800506ab  jnz     short loc_1800506C5
0x1800506ad  mov     rcx, rsi
0x1800506b0  call    BfspIsSetupObject
0x1800506b5  movzx   ecx, r8b
0x1800506b9  test    al, al
0x1800506bb  cmovnz  ecx, r9d
0x1800506bf  mov     r8b, cl
0x1800506c2  mov     [rbp+arg_10], cl
0x1800506c5  test    r8b, r8b
0x1800506c8  jnz     short loc_1800506E1
0x1800506ca  mov     rcx, [rbp+var_40]
0x1800506ce  call    cs:__imp_BcdCloseObject
0x1800506d4  mov     [rbp+var_40], 0
0x1800506dc  jmp     loc_18005077D
0x1800506e1  lea     rdx, [rbp+DestinationString]; GuidString
0x1800506e5  mov     rcx, rsi; Guid
0x1800506e8  call    cs:__imp_RtlStringFromGUID
0x1800506ee  lea     r8, [rbp+DestinationString]
0x1800506f2  mov     ecx, 2
0x1800506f7  lea     rdx, aRemovingDuplic; "Removing duplicate object %wZ"
0x1800506fe  call    BfspLogMessage
0x180050703  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180050707  call    cs:__imp_RtlFreeUnicodeString
0x18005070d  mov     rcx, [rbp+var_40]
0x180050711  call    cs:__imp_BcdDeleteObject
0x180050717  mov     [rbp+var_40], 0
0x18005071f  mov     ebx, eax
0x180050721  test    eax, eax
0x180050723  js      loc_1800507DE
0x180050729  lea     r8, [rbp+var_30]
0x18005072d  mov     rcx, r15
0x180050730  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180050737  call    cs:__imp_BcdOpenObject
0x18005073d  test    eax, eax
0x18005073f  js      short loc_18005077D
0x180050741  mov     rcx, [rbp+var_30]
0x180050745  mov     r8, rsi
0x180050748  call    BfspDeleteObjectFromDisplayOrder
0x18005074d  mov     rcx, [rbp+var_30]
0x180050751  mov     ebx, eax
0x180050753  call    cs:__imp_BcdCloseObject
0x180050759  test    ebx, ebx
0x18005075b  jns     short loc_18005077D
0x18005075d  mov     rcx, rsi
0x180050760  call    BfspIsSetupObject
0x180050765  test    al, al
0x180050767  jnz     short loc_18005077D
0x180050769  mov     r8d, ebx
0x18005076c  lea     rdx, aFailedToRemove; "Failed to remove duplicate object from "...
0x180050773  mov     ecx, 3
0x180050778  call    BfspLogMessage
0x18005077d  inc     r14d
0x180050780  cmp     r14d, [rbp+arg_18]
0x180050784  jb      loc_180050640
0x18005078a  xor     ebx, ebx
0x18005078c  mov     rcx, [rbp+var_40]
0x180050790  test    rcx, rcx
0x180050793  jz      short loc_18005079B
0x180050795  call    cs:__imp_BcdCloseObject
0x18005079b  test    rdi, rdi
0x18005079e  jz      short loc_1800507B4
0x1800507a0  call    cs:__imp_GetProcessHeap
0x1800507a6  mov     r8, rdi; lpMem
0x1800507a9  xor     edx, edx; dwFlags
0x1800507ab  mov     rcx, rax; hHeap
0x1800507ae  call    cs:__imp_HeapFree
0x1800507b4  mov     rcx, [rbp+var_20]
0x1800507b8  test    rcx, rcx
0x1800507bb  jz      short loc_1800507C3
0x1800507bd  call    cs:__imp_BcdCloseObject
0x1800507c3  mov     eax, ebx
0x1800507c5  lea     r11, [rsp+70h+var_s0]
0x1800507ca  mov     rbx, [r11+30h]
0x1800507ce  mov     rsi, [r11+38h]
0x1800507d2  mov     rsp, r11
0x1800507d5  pop     r15
0x1800507d7  pop     r14
0x1800507d9  pop     r13
0x1800507db  pop     rdi
0x1800507dc  pop     rbp
0x1800507dd  retn
0x1800507de  lea     rdx, aFailedToDelete_1; "Failed to delete duplicate loader objec"...
0x1800507e5  jmp     loc_1800505F1
0x1800507ea  lea     rdx, aFailedToGetAHa_1; "Failed to get a handle to the OS loader"...
0x1800507f1  jmp     loc_1800505F1
```
