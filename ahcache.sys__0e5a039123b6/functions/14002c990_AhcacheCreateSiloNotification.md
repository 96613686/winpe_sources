# AhcacheCreateSiloNotification

- ea: `0x14002c990`
- end: `0x14002cad3`
- name: `AhcacheCreateSiloNotification`
- size: `323`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007e40`
- `0x14002a3dc`
- `0x14002c990`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!PsCreateSiloContext` at `0x14002c9bd`
- `ntoskrnl!PsCreateSiloContext` at `0x14002c9bd`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14002c9ef`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14002c9ef`
- `ntoskrnl!PsGetHostSilo` at `0x14002ca5e`
- `ntoskrnl!PsGetHostSilo` at `0x14002ca5e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14002cab9`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14002cab9`

## string_xrefs

- `0x14002c9cf`: `PsCreateSiloContext failed: 0x%x\n`
- `0x14002ca9a`: `AhcacheCreateSiloNotification`
- `0x14002ca8d`: `Failed to initialize apphelp cache [%x]`

## pseudocode

```c
__int64 __fastcall AhcacheCreateSiloNotification(__int64 a1)
{
  int inserted; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  __int64 v7; // [rsp+20h] [rbp-18h]
  void *v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  inserted = PsCreateSiloContext(a1, 728, 512, 0, &v8);
  v3 = inserted;
  if ( inserted >= 0 )
  {
    inserted = PsInsertPermanentSiloContext(a1, (unsigned int)g_AhcacheSiloContextSlot, v8);
    v3 = inserted;
    if ( inserted >= 0 )
    {
      memset(v8, 0, 0x2D8u);
      *((_QWORD *)v8 + 14) = 3600000;
      *((_DWORD *)v8 + 174) = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
      *((_DWORD *)v8 + 176) = a1 != PsGetHostSilo();
      inserted = AhcInitialize(v8);
      v3 = inserted;
      if ( inserted >= 0 )
        goto LABEL_8;
      v4 = "Failed to initialize apphelp cache [%x]";
      v5 = 376;
    }
    else
    {
      v4 = "PsInsertPermanentSiloContext failed: 0x%x\n";
      v5 = 351;
    }
  }
  else
  {
    v4 = "PsCreateSiloContext failed: 0x%x\n";
    v5 = 337;
  }
  LODWORD(v7) = inserted;
  AslLogCallPrintf(1, "AhcacheCreateSiloNotification", v5, v4, v7);
LABEL_8:
  if ( v8 )
    PsDereferenceSiloContext();
  return v3;
}

```

## disassembly

```asm
0x14002c990  mov     r11, rsp
0x14002c993  mov     [r11+8], rbx
0x14002c997  push    rdi
0x14002c998  sub     rsp, 30h
0x14002c99c  lea     rax, [r11+10h]
0x14002c9a0  mov     qword ptr [r11+10h], 0
0x14002c9a8  xor     r9d, r9d
0x14002c9ab  mov     [r11-18h], rax
0x14002c9af  mov     edx, 2D8h
0x14002c9b4  mov     r8d, 200h
0x14002c9ba  mov     rdi, rcx
0x14002c9bd  call    cs:__imp_PsCreateSiloContext
0x14002c9c4  nop     dword ptr [rax+rax+00h]
0x14002c9c9  mov     ebx, eax
0x14002c9cb  test    eax, eax
0x14002c9cd  jns     short loc_14002C9E1
0x14002c9cf  lea     r9, aPscreatesiloco; "PsCreateSiloContext failed: 0x%x\n"
0x14002c9d6  mov     r8d, 151h
0x14002c9dc  jmp     loc_14002CA9A
0x14002c9e1  mov     r8, [rsp+38h+arg_8]
0x14002c9e6  mov     rcx, rdi
0x14002c9e9  mov     edx, cs:g_AhcacheSiloContextSlot
0x14002c9ef  call    cs:__imp_PsInsertPermanentSiloContext
0x14002c9f6  nop     dword ptr [rax+rax+00h]
0x14002c9fb  mov     ebx, eax
0x14002c9fd  test    eax, eax
0x14002c9ff  jns     short loc_14002CA13
0x14002ca01  lea     r9, aPsinsertperman; "PsInsertPermanentSiloContext failed: 0x"...
0x14002ca08  mov     r8d, 15Fh
0x14002ca0e  jmp     loc_14002CA9A
0x14002ca13  mov     rcx, [rsp+38h+arg_8]; void *
0x14002ca18  xor     edx, edx; Val
0x14002ca1a  mov     r8d, 2D8h; Size
0x14002ca20  call    memset
0x14002ca25  mov     rax, [rsp+38h+arg_8]
0x14002ca2a  mov     rcx, 0FFFFF78000000004h
0x14002ca34  mov     qword ptr [rax+70h], 36EE80h
0x14002ca3c  mov     rax, 0FFFFF78000000320h
0x14002ca46  mov     rax, [rax]
0x14002ca49  mov     ecx, [rcx]
0x14002ca4b  imul    rcx, rax
0x14002ca4f  mov     rax, [rsp+38h+arg_8]
0x14002ca54  shr     rcx, 18h
0x14002ca58  mov     [rax+2B8h], ecx
0x14002ca5e  call    cs:__imp_PsGetHostSilo
0x14002ca65  nop     dword ptr [rax+rax+00h]
0x14002ca6a  xor     ecx, ecx
0x14002ca6c  cmp     rdi, rax
0x14002ca6f  mov     rax, [rsp+38h+arg_8]
0x14002ca74  setnz   cl
0x14002ca77  mov     [rax+2C0h], ecx
0x14002ca7d  mov     rcx, [rsp+38h+arg_8]
0x14002ca82  call    AhcInitialize
0x14002ca87  mov     ebx, eax
0x14002ca89  test    eax, eax
0x14002ca8b  jns     short loc_14002CAAF
0x14002ca8d  lea     r9, aFailedToInitia; "Failed to initialize apphelp cache [%x]"
0x14002ca94  mov     r8d, 178h
0x14002ca9a  lea     rdx, aAhcachecreates; "AhcacheCreateSiloNotification"
0x14002caa1  mov     dword ptr [rsp+38h+var_18], eax
0x14002caa5  mov     ecx, 1
0x14002caaa  call    AslLogCallPrintf
0x14002caaf  mov     rcx, [rsp+38h+arg_8]
0x14002cab4  test    rcx, rcx
0x14002cab7  jz      short loc_14002CAC5
0x14002cab9  call    cs:__imp_PsDereferenceSiloContext
0x14002cac0  nop     dword ptr [rax+rax+00h]
0x14002cac5  mov     eax, ebx
0x14002cac7  mov     rbx, [rsp+38h+arg_0]
0x14002cacc  add     rsp, 30h
0x14002cad0  pop     rdi
0x14002cad1  retn
```
