# BiOpenSystemStore

- ea: `0x14001bd44`
- end: `0x14001c00d`
- name: `BiOpenSystemStore`
- size: `713`
- prototype: `__int64 __fastcall(__int64 *, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x14001ae30`
- `0x14001bb00`

## callees

- `0x1400133e4`
- `0x14001b354`
- `0x14001b4bc`
- `0x14001b64c`
- `0x14001b764`
- `0x14001bd44`
- `0x14001c0d4`
- `0x14001c3a8`
- `0x14001e5e4`
- `0x14001ece0`
- `0x14001ee20`
- `0x14001f980`
- `0x14001fb48`
- `0x1400215cc`
- `0x1400221ac`
- `0x140027010`

## import_xrefs

- `msvcrt!wcstoul` at `0x14001be19`
- `msvcrt!wcstoul` at `0x14001be19`
- `msvcrt!_wcsnicmp` at `0x14001be01`
- `msvcrt!_wcsnicmp` at `0x14001be01`
- `ntdll!ZwClose` at `0x14001bff6`
- `ntdll!ZwClose` at `0x14001bff6`
- `ntdll!RtlFreeHeap` at `0x14001bfe5`
- `ntdll!RtlFreeHeap` at `0x14001bfe5`

## string_xrefs

- `0x14001bd78`: `Opening system store. Flags: 0x%x`
- `0x14001bda7`: `\Registry\Machine`
- `0x14001be93`: `The system store is not already loaded`
- `0x14001beb2`: `Specified flags prevent opening unloaded system store`

## pseudocode

```c
__int64 __fastcall BiOpenSystemStore(__int64 *a1, unsigned int a2)
{
  __int64 v2; // rdi
  int v4; // ebx
  int v5; // eax
  const wchar_t **v6; // rsi
  unsigned int v7; // r15d
  __int64 v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // r15d
  __int64 v12; // r14
  int v13; // eax
  void *v14; // r8
  int v15; // eax
  int v16; // eax
  HANDLE Handle; // [rsp+30h] [rbp-10h] BYREF
  ULONG v20; // [rsp+88h] [rbp+48h] BYREF
  PVOID P; // [rsp+90h] [rbp+50h] BYREF
  HANDLE v22; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  *a1 = 0;
  v20 = 0;
  Handle = 0;
  v22 = 0;
  P = 0;
  BiLogMessage(2, L"Opening system store. Flags: 0x%x", a2);
  BiCleanupLoadedStores(16 * (a2 & 1));
  v4 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 0xF003Fu, &Handle);
  if ( v4 < 0 )
    goto LABEL_39;
  v5 = BiEnumerateSubKeys((unsigned __int64)Handle, (char **)&P, &v20);
  v6 = (const wchar_t **)P;
  v4 = v5;
  if ( v5 < 0 )
    goto LABEL_37;
  v7 = v20;
  v8 = 0;
  LODWORD(P) = 0;
  if ( !v20 )
    goto LABEL_12;
  while ( 1 )
  {
    if ( _wcsnicmp(v6[v8], L"BCD", 3u) )
      goto LABEL_9;
    if ( wcstoul(v6[v8] + 3, 0, 10) == -1 )
      goto LABEL_9;
    BiLogMessage(2, L"Found loaded store at key %s", v6[v8]);
    v9 = BiOpenKey((unsigned __int64)Handle, v6[v8], 0x20019u, &v22);
    v2 = (__int64)v22;
    if ( v9 < 0 )
      goto LABEL_9;
    if ( BiIsSystemStore((unsigned __int64)v22) )
      break;
    BiCloseKey((HANDLE)v2);
LABEL_9:
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= v7 )
      goto LABEL_12;
  }
  BiLogMessage(2, L"Store %s is the system store", v6[v8]);
LABEL_12:
  if ( (_DWORD)v8 != v7 )
  {
    v11 = (int)P;
LABEL_19:
    if ( (a2 & 2) != 0 )
    {
      v2 |= 2uLL;
    }
    else
    {
      v12 = (unsigned __int8)BiWasFirmwareModified(v2);
      BiLogMessage(2, L"Synchronizing store with firmware. FirmwareModified: %d", v12);
      v13 = BiGetFirmwareType(0) - 1;
      if ( v13 )
      {
        v15 = v13 - 1;
        if ( v15 )
        {
          if ( v15 != 1 )
          {
            v4 = -1073741637;
LABEL_25:
            BiLogMessage(4, L"Failed to bind with firmware. Flags: 0x%x Status: %x", a2, (unsigned int)v4);
            goto LABEL_33;
          }
        }
        else
        {
          v4 = BiBindEfiNamespaceObjects(v2);
          if ( v4 < 0 )
            goto LABEL_25;
        }
      }
      if ( !(_BYTE)v12 )
        BiDeleteRegistryValue(v2, L"FirmwareModified", v14);
    }
    if ( (unsigned __int8)BiFilterIsPolicyActive() )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))qword_14003F848)(0, 0, 0, 0, 0);
      v4 = 0;
      if ( v16 != -2143092730 )
        v4 = v16;
      if ( v4 < 0 )
        goto LABEL_33;
    }
    else
    {
      v4 = 0;
    }
    *a1 = v2;
    goto LABEL_37;
  }
  BiLogMessage(2, L"The system store is not already loaded");
  v22 = 0;
  if ( (a2 & 4) != 0 )
  {
    BiLogMessage(4, L"Specified flags prevent opening unloaded system store");
    v4 = -1073741275;
    goto LABEL_37;
  }
  v10 = BiLoadSystemStore(&v22);
  v2 = (__int64)v22;
  v4 = v10;
  if ( v10 >= 0 )
  {
    v11 = 1;
    goto LABEL_19;
  }
  v11 = (int)P;
LABEL_33:
  if ( v2 )
    BiCloseStore(v2, v11 != 0 ? 2 : 0);
LABEL_37:
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
LABEL_39:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001bd44  mov     [rsp-38h+arg_0], rcx
0x14001bd49  push    rbp
0x14001bd4a  push    rbx
0x14001bd4b  push    rsi
0x14001bd4c  push    rdi
0x14001bd4d  push    r12
0x14001bd4f  push    r14
0x14001bd51  push    r15
0x14001bd53  mov     rbp, rsp
0x14001bd56  sub     rsp, 40h
0x14001bd5a  xor     edi, edi
0x14001bd5c  mov     qword ptr [rcx], 0
0x14001bd63  mov     r12d, edx
0x14001bd66  mov     [rbp+arg_8], 0
0x14001bd6d  mov     r8d, edx
0x14001bd70  mov     [rbp+Handle], 0
0x14001bd78  lea     rdx, aOpeningSystemS; "Opening system store. Flags: 0x%x"
0x14001bd7f  mov     [rbp+arg_18], rdi
0x14001bd83  lea     ecx, [rdi+2]
0x14001bd86  mov     [rbp+P], rdi
0x14001bd8a  call    BiLogMessage
0x14001bd8f  mov     ecx, r12d
0x14001bd92  and     ecx, 1
0x14001bd95  shl     ecx, 4
0x14001bd98  call    BiCleanupLoadedStores
0x14001bd9d  lea     r9, [rbp+Handle]
0x14001bda1  mov     r8d, 0F003Fh
0x14001bda7  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x14001bdae  xor     ecx, ecx
0x14001bdb0  call    BiOpenKeyNonBcd
0x14001bdb5  mov     ebx, eax
0x14001bdb7  test    eax, eax
0x14001bdb9  js      loc_14001BFEB
0x14001bdbf  mov     rcx, [rbp+Handle]
0x14001bdc3  lea     r8, [rbp+arg_8]
0x14001bdc7  lea     rdx, [rbp+P]
0x14001bdcb  call    BiEnumerateSubKeys
0x14001bdd0  mov     rsi, [rbp+P]
0x14001bdd4  mov     ebx, eax
0x14001bdd6  test    eax, eax
0x14001bdd8  js      loc_14001BFCE
0x14001bdde  mov     r15d, [rbp+arg_8]
0x14001bde2  xor     ebx, ebx
0x14001bde4  mov     dword ptr [rbp+P], edi
0x14001bde7  test    r15d, r15d
0x14001bdea  jz      loc_14001BE8E
0x14001bdf0  mov     rcx, [rsi+rbx*8]; String1
0x14001bdf4  lea     rdx, aBcd; "BCD"
0x14001bdfb  mov     r8d, 3; MaxCount
0x14001be01  call    cs:__imp__wcsnicmp
0x14001be07  test    eax, eax
0x14001be09  jnz     short loc_14001BE6C
0x14001be0b  mov     rcx, [rsi+rbx*8]
0x14001be0f  lea     r8d, [rax+0Ah]; Radix
0x14001be13  add     rcx, 6; String
0x14001be17  xor     edx, edx; EndPtr
0x14001be19  call    cs:__imp_wcstoul
0x14001be1f  cmp     eax, 0FFFFFFFFh
0x14001be22  jz      short loc_14001BE6C
0x14001be24  mov     r8, [rsi+rbx*8]
0x14001be28  lea     rdx, aFoundLoadedSto; "Found loaded store at key %s"
0x14001be2f  mov     ecx, 2
0x14001be34  call    BiLogMessage
0x14001be39  mov     rdx, [rsi+rbx*8]
0x14001be3d  lea     r9, [rbp+arg_18]
0x14001be41  mov     rcx, [rbp+Handle]
0x14001be45  mov     r8d, 20019h
0x14001be4b  call    BiOpenKey
0x14001be50  mov     rdi, [rbp+arg_18]
0x14001be54  test    eax, eax
0x14001be56  js      short loc_14001BE6C
0x14001be58  mov     rcx, rdi
0x14001be5b  call    BiIsSystemStore
0x14001be60  test    al, al
0x14001be62  jnz     short loc_14001BE79
0x14001be64  mov     rcx, rdi; Handle
0x14001be67  call    BiCloseKey
0x14001be6c  inc     ebx
0x14001be6e  cmp     ebx, r15d
0x14001be71  jb      loc_14001BDF0
0x14001be77  jmp     short loc_14001BE8E
0x14001be79  mov     r8, [rsi+rbx*8]
0x14001be7d  lea     rdx, aStoreSIsTheSys; "Store %s is the system store"
0x14001be84  mov     ecx, 2
0x14001be89  call    BiLogMessage
0x14001be8e  cmp     ebx, r15d
0x14001be91  jnz     short loc_14001BEF1
0x14001be93  lea     rdx, aTheSystemStore; "The system store is not already loaded"
0x14001be9a  mov     ecx, 2
0x14001be9f  call    BiLogMessage
0x14001bea4  mov     [rbp+arg_18], 0
0x14001beac  test    r12b, 4
0x14001beb0  jz      short loc_14001BECD
0x14001beb2  lea     rdx, aSpecifiedFlags; "Specified flags prevent opening unloade"...
0x14001beb9  mov     ecx, 4
0x14001bebe  call    BiLogMessage
0x14001bec3  mov     ebx, 0C0000225h
0x14001bec8  jmp     loc_14001BFCE
0x14001becd  lea     rcx, [rbp+arg_18]
0x14001bed1  call    BiLoadSystemStore
0x14001bed6  mov     rdi, [rbp+arg_18]
0x14001beda  mov     ebx, eax
0x14001bedc  test    eax, eax
0x14001bede  js      short loc_14001BEE8
0x14001bee0  mov     r15d, 1
0x14001bee6  jmp     short loc_14001BEF5
0x14001bee8  mov     r15d, dword ptr [rbp+P]
0x14001beec  jmp     loc_14001BFAE
0x14001bef1  mov     r15d, dword ptr [rbp+P]
0x14001bef5  test    r12b, 2
0x14001bef9  jnz     short loc_14001BF75
0x14001befb  mov     rcx, rdi
0x14001befe  call    BiWasFirmwareModified
0x14001bf03  movzx   r14d, al
0x14001bf07  lea     rdx, aSynchronizingS; "Synchronizing store with firmware. Firm"...
0x14001bf0e  mov     r8d, r14d
0x14001bf11  mov     ecx, 2
0x14001bf16  call    BiLogMessage
0x14001bf1b  xor     ecx, ecx
0x14001bf1d  call    BiGetFirmwareType
0x14001bf22  sub     eax, 1
0x14001bf25  jz      short loc_14001BF5F
0x14001bf27  sub     eax, 1
0x14001bf2a  jz      short loc_14001BF38
0x14001bf2c  cmp     eax, 1
0x14001bf2f  jz      short loc_14001BF5F
0x14001bf31  mov     ebx, 0C00000BBh
0x14001bf36  jmp     short loc_14001BF46
0x14001bf38  mov     rcx, rdi
0x14001bf3b  call    BiBindEfiNamespaceObjects
0x14001bf40  mov     ebx, eax
0x14001bf42  test    eax, eax
0x14001bf44  jns     short loc_14001BF5F
0x14001bf46  mov     r9d, ebx
0x14001bf49  lea     rdx, aFailedToBindWi; "Failed to bind with firmware. Flags: 0x"...
0x14001bf50  mov     r8d, r12d
0x14001bf53  mov     ecx, 4
0x14001bf58  call    BiLogMessage
0x14001bf5d  jmp     short loc_14001BFAE
0x14001bf5f  test    r14b, r14b
0x14001bf62  jnz     short loc_14001BF79
0x14001bf64  lea     rdx, aFirmwaremodifi; "FirmwareModified"
0x14001bf6b  mov     rcx, rdi
0x14001bf6e  call    BiDeleteRegistryValue
0x14001bf73  jmp     short loc_14001BF79
0x14001bf75  or      rdi, 2
0x14001bf79  call    BiFilterIsPolicyActive
0x14001bf7e  test    al, al
0x14001bf80  jz      short loc_14001BFC5
0x14001bf82  mov     rax, cs:qword_14003F848
0x14001bf89  xor     r9d, r9d
0x14001bf8c  xor     r8d, r8d
0x14001bf8f  mov     [rsp+40h+var_20], 0
0x14001bf97  xor     edx, edx
0x14001bf99  xor     ecx, ecx
0x14001bf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfa0  xor     ebx, ebx
0x14001bfa2  cmp     eax, 80430006h
0x14001bfa7  cmovnz  ebx, eax
0x14001bfaa  test    ebx, ebx
0x14001bfac  jns     short loc_14001BFC7
0x14001bfae  test    rdi, rdi
0x14001bfb1  jz      short loc_14001BFCE
0x14001bfb3  neg     r15d
0x14001bfb6  mov     rcx, rdi
0x14001bfb9  sbb     edx, edx
0x14001bfbb  and     edx, 2
0x14001bfbe  call    BiCloseStore
0x14001bfc3  jmp     short loc_14001BFCE
0x14001bfc5  xor     ebx, ebx
0x14001bfc7  mov     rax, [rbp+arg_0]
0x14001bfcb  mov     [rax], rdi
0x14001bfce  test    rsi, rsi
0x14001bfd1  jz      short loc_14001BFEB
0x14001bfd3  mov     rcx, gs:60h
0x14001bfdc  mov     r8, rsi; P
0x14001bfdf  xor     edx, edx; Flags
0x14001bfe1  mov     rcx, [rcx+30h]; HeapHandle
0x14001bfe5  call    cs:__imp_RtlFreeHeap
0x14001bfeb  cmp     [rbp+Handle], 0
0x14001bff0  jz      short loc_14001BFFC
0x14001bff2  mov     rcx, [rbp+Handle]; Handle
0x14001bff6  call    cs:__imp_ZwClose
0x14001bffc  mov     eax, ebx
0x14001bffe  add     rsp, 40h
0x14001c002  pop     r15
0x14001c004  pop     r14
0x14001c006  pop     r12
0x14001c008  pop     rdi
0x14001c009  pop     rsi
0x14001c00a  pop     rbx
0x14001c00b  pop     rbp
0x14001c00c  retn
```
