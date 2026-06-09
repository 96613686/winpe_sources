# BiBindEfiBootManager

- ea: `0x140021c10`
- end: `0x140021f52`
- name: `BiBindEfiBootManager`
- size: `834`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x1400221ac`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x140013b9c`
- `0x140013ee8`
- `0x140014130`
- `0x140018b54`
- `0x14001ae94`
- `0x14001c014`
- `0x14001c6e4`
- `0x14001fc5c`
- `0x140021c10`
- `0x140024714`
- `0x14002483c`
- `0x140024ac8`
- `0x140026650`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140021da4`
- `ntdll!RtlAllocateHeap` at `0x140021da4`
- `ntdll!RtlFreeHeap` at `0x140021eb9`
- `ntdll!RtlFreeHeap` at `0x140021ed6`
- `ntdll!RtlFreeHeap` at `0x140021ef3`
- `ntdll!RtlFreeHeap` at `0x140021eb9`
- `ntdll!RtlFreeHeap` at `0x140021ed6`
- `ntdll!RtlFreeHeap` at `0x140021ef3`

## string_xrefs

- `0x140021cd5`: `BcdCreateObject: Failed to acquire BCD sync mutant. Status: %x`

## pseudocode

```c
__int64 __fastcall BiBindEfiBootManager(__int64 a1, __int64 a2)
{
  unsigned int *v3; // r15
  unsigned int *v4; // rsi
  char *Heap; // r12
  HANDLE v6; // rdi
  NTSTATUS v7; // eax
  int v8; // ebx
  int Object; // eax
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // esi
  int v13; // ebx
  __int64 v14; // r14
  __int64 v15; // r13
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  __int64 v19; // rdx
  HANDLE Handle; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-31h] BYREF
  int v23; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int64 v24; // [rsp+40h] [rbp-29h] BYREF
  unsigned int *v25; // [rsp+48h] [rbp-21h] BYREF
  PVOID P; // [rsp+50h] [rbp-19h] BYREF
  __int64 v27; // [rsp+58h] [rbp-11h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h]
  __int64 v29; // [rsp+68h] [rbp-1h]
  __int128 v30; // [rsp+70h] [rbp+7h] BYREF

  v28 = a2;
  v29 = a1;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v27 = 0;
  v30 = 0;
  v3 = 0;
  P = 0;
  v4 = 0;
  v25 = 0;
  Handle = 0;
  Heap = 0;
  BiLogMessage(1, L"BiBindEfiBootManager");
  if ( (int)BcdOpenObject(a1, &GUID_FIRMWARE_BOOTMGR, &Handle) < 0 )
  {
    v6 = Handle;
  }
  else
  {
    BcdDeleteObject((__int64)Handle);
    v6 = 0;
    Handle = 0;
  }
  v24 = 0x1010000100000001LL;
  v7 = BiAcquireBcdSyncMutant(a1 & 1);
  v8 = v7;
  if ( v7 < 0 )
  {
    BiLogMessage(4, L"BcdCreateObject: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v7);
LABEL_28:
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    goto LABEL_30;
  }
  Object = BiCreateObject(a1, (unsigned int)&GUID_FIRMWARE_BOOTMGR, (unsigned int)&v24, 0, (__int64)&Handle);
  v6 = Handle;
  v8 = Object;
  if ( Object >= 0 && (unsigned __int8)BiIsLinkedToFirmwareVariable(Handle, 0) )
  {
    LODWORD(Handle) = 1;
    BiSetRegistryValue(v29, L"FirmwareModified", L"Description", 4, &Handle, 4);
  }
  LOBYTE(v10) = a1 & 1;
  BiReleaseBcdSyncMutant(v10);
  if ( v8 < 0 )
    goto LABEL_28;
  v11 = BiQueryBootEntryOrder(&P, &v22);
  v3 = (unsigned int *)P;
  v8 = v11;
  if ( v11 < 0 )
    goto LABEL_30;
  v12 = v22;
  if ( !v22 )
    goto LABEL_21;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * v22);
  if ( !Heap )
  {
    v8 = -1073741670;
    goto LABEL_30;
  }
  v13 = 0;
  v14 = 0;
  if ( !v12 )
    goto LABEL_21;
  v15 = v28;
  do
  {
    v16 = BiTranslateBootEntryId(v15, v3[v14], &Heap[16 * v13]);
    v17 = v13 + 1;
    if ( v16 < 0 )
      v17 = v13;
    v14 = (unsigned int)(v14 + 1);
    v13 = v17;
  }
  while ( (unsigned int)v14 < v12 );
  if ( !v17 || (v8 = BcdSetElementDataWithFlags((__int64)v6, 603979777, 0, (__int64)Heap, 16 * v17), v8 >= 0) )
  {
LABEL_21:
    v18 = BiQueryBootOptions(&v25, &v23);
    v4 = v25;
    v8 = v18;
    if ( v18 >= 0 )
    {
      if ( v25[2] == -1
        || (v27 = v25[2], v8 = BcdSetElementDataWithFlags((__int64)v6, 620756996, 0, (__int64)&v27, 8u), v8 >= 0) )
      {
        v19 = v4[4];
        if ( (_DWORD)v19 == -2
          || (int)BiTranslateBootEntryId(v28, v19, &v30) < 0
          || (v8 = BcdSetElementDataWithFlags((__int64)v6, 603979778, 0, (__int64)&v30, 0x10u), v8 >= 0) )
        {
          v8 = 0;
        }
      }
    }
    goto LABEL_28;
  }
LABEL_30:
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v6 )
  {
    if ( v8 < 0 )
    {
      BcdDeleteObject((__int64)v6);
LABEL_39:
      BiLogMessage(4, L"BiBindEfiBootManager failed %x", (unsigned int)v8);
      return (unsigned int)v8;
    }
    BcdCloseObject(v6);
  }
  else if ( v8 < 0 )
  {
    goto LABEL_39;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140021c10  mov     [rsp-8+arg_10], rbx
0x140021c15  push    rbp
0x140021c16  push    rsi
0x140021c17  push    rdi
0x140021c18  push    r12
0x140021c1a  push    r13
0x140021c1c  push    r14
0x140021c1e  push    r15
0x140021c20  lea     rbp, [rsp-27h]
0x140021c25  sub     rsp, 90h
0x140021c2c  mov     rax, cs:__security_cookie
0x140021c33  xor     rax, rsp
0x140021c36  mov     [rbp+57h+var_40], rax
0x140021c3a  xor     ebx, ebx
0x140021c3c  mov     [rbp+57h+var_60], rdx
0x140021c40  mov     r13, rcx
0x140021c43  mov     [rbp+57h+var_58], rcx
0x140021c47  xorps   xmm0, xmm0
0x140021c4a  mov     [rbp+57h+var_84], ebx
0x140021c4d  lea     rdx, aBibindefibootm; "BiBindEfiBootManager"
0x140021c54  mov     [rbp+57h+var_88], ebx
0x140021c57  lea     r14d, [rbx+1]
0x140021c5b  mov     [rbp+57h+var_80], rbx
0x140021c5f  mov     ecx, r14d
0x140021c62  mov     [rbp+57h+var_68], rbx
0x140021c66  movups  [rbp+57h+var_50], xmm0
0x140021c6a  mov     r15d, ebx
0x140021c6d  mov     [rbp+57h+P], rbx
0x140021c71  mov     esi, ebx
0x140021c73  mov     [rbp+57h+var_78], rbx
0x140021c77  mov     [rbp+57h+Handle], rbx
0x140021c7b  mov     r12d, ebx
0x140021c7e  call    BiLogMessage
0x140021c83  lea     r8, [rbp+57h+Handle]
0x140021c87  mov     rcx, r13
0x140021c8a  lea     rdx, GUID_FIRMWARE_BOOTMGR
0x140021c91  call    BcdOpenObject
0x140021c96  test    eax, eax
0x140021c98  js      short loc_140021CAB
0x140021c9a  mov     rcx, [rbp+57h+Handle]
0x140021c9e  call    BcdDeleteObject
0x140021ca3  mov     edi, ebx
0x140021ca5  mov     [rbp+57h+Handle], rbx
0x140021ca9  jmp     short loc_140021CAF
0x140021cab  mov     rdi, [rbp+57h+Handle]
0x140021caf  mov     dword ptr [rbp+57h+var_80], r14d
0x140021cb3  mov     r14b, r13b
0x140021cb6  and     r14b, 1
0x140021cba  mov     dword ptr [rbp+57h+var_80+4], 10100001h
0x140021cc1  mov     cl, r14b
0x140021cc4  call    BiAcquireBcdSyncMutant
0x140021cc9  mov     ebx, eax
0x140021ccb  test    eax, eax
0x140021ccd  jns     short loc_140021CEC
0x140021ccf  mov     r13d, 4
0x140021cd5  lea     rdx, aBcdcreateobjec; "BcdCreateObject: Failed to acquire BCD "...
0x140021cdc  mov     ecx, r13d
0x140021cdf  mov     r8d, eax
0x140021ce2  call    BiLogMessage
0x140021ce7  jmp     loc_140021EA2
0x140021cec  lea     rax, [rbp+57h+Handle]
0x140021cf0  xor     r9d, r9d
0x140021cf3  lea     r8, [rbp+57h+var_80]
0x140021cf7  mov     [rsp+0C0h+var_A0], rax
0x140021cfc  lea     rdx, GUID_FIRMWARE_BOOTMGR
0x140021d03  mov     rcx, r13
0x140021d06  call    BiCreateObject
0x140021d0b  mov     rdi, [rbp+57h+Handle]
0x140021d0f  mov     ebx, eax
0x140021d11  mov     r13d, 4
0x140021d17  test    eax, eax
0x140021d19  js      short loc_140021D58
0x140021d1b  xor     edx, edx
0x140021d1d  mov     rcx, rdi
0x140021d20  call    BiIsLinkedToFirmwareVariable
0x140021d25  test    al, al
0x140021d27  jz      short loc_140021D58
0x140021d29  mov     rcx, [rbp+57h+var_58]
0x140021d2d  lea     rax, [rbp+57h+Handle]
0x140021d31  mov     [rsp+0C0h+var_98], r13d
0x140021d36  lea     r8, aDescription; "Description"
0x140021d3d  mov     r9d, r13d
0x140021d40  mov     [rsp+0C0h+var_A0], rax
0x140021d45  lea     rdx, aFirmwaremodifi; "FirmwareModified"
0x140021d4c  mov     dword ptr [rbp+57h+Handle], 1
0x140021d53  call    BiSetRegistryValue
0x140021d58  mov     cl, r14b
0x140021d5b  call    BiReleaseBcdSyncMutant
0x140021d60  test    ebx, ebx
0x140021d62  js      loc_140021EA2
0x140021d68  lea     rdx, [rbp+57h+var_88]
0x140021d6c  lea     rcx, [rbp+57h+P]
0x140021d70  call    BiQueryBootEntryOrder
0x140021d75  mov     r15, [rbp+57h+P]
0x140021d79  mov     ebx, eax
0x140021d7b  test    eax, eax
0x140021d7d  js      loc_140021EBF
0x140021d83  mov     esi, [rbp+57h+var_88]
0x140021d86  test    esi, esi
0x140021d88  jz      loc_140021E1F
0x140021d8e  mov     rcx, gs:60h
0x140021d97  mov     r8d, esi
0x140021d9a  shl     r8, 4; Size
0x140021d9e  xor     edx, edx; Flags
0x140021da0  mov     rcx, [rcx+30h]; HeapHandle
0x140021da4  call    cs:__imp_RtlAllocateHeap
0x140021daa  mov     r12, rax
0x140021dad  test    rax, rax
0x140021db0  jnz     short loc_140021DBC
0x140021db2  mov     ebx, 0C000009Ah
0x140021db7  jmp     loc_140021EBF
0x140021dbc  xor     ebx, ebx
0x140021dbe  xor     r14d, r14d
0x140021dc1  test    esi, esi
0x140021dc3  jz      short loc_140021E1F
0x140021dc5  mov     r13, [rbp+57h+var_60]
0x140021dc9  mov     edx, [r15+r14*4]
0x140021dcd  mov     rcx, r13
0x140021dd0  mov     r8d, ebx
0x140021dd3  shl     r8, 4
0x140021dd7  add     r8, r12
0x140021dda  call    BiTranslateBootEntryId
0x140021ddf  test    eax, eax
0x140021de1  lea     ecx, [rbx+1]
0x140021de4  cmovs   ecx, ebx
0x140021de7  inc     r14d
0x140021dea  mov     ebx, ecx
0x140021dec  cmp     r14d, esi
0x140021def  jb      short loc_140021DC9
0x140021df1  mov     r13d, 4
0x140021df7  test    ecx, ecx
0x140021df9  jz      short loc_140021E1F
0x140021dfb  shl     ebx, 4
0x140021dfe  mov     r9, r12
0x140021e01  xor     r8d, r8d
0x140021e04  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x140021e08  mov     edx, 24000001h
0x140021e0d  mov     rcx, rdi
0x140021e10  call    BcdSetElementDataWithFlags
0x140021e15  mov     ebx, eax
0x140021e17  test    eax, eax
0x140021e19  js      loc_140021EBF
0x140021e1f  lea     rdx, [rbp+57h+var_84]
0x140021e23  lea     rcx, [rbp+57h+var_78]
0x140021e27  call    BiQueryBootOptions
0x140021e2c  mov     rsi, [rbp+57h+var_78]
0x140021e30  mov     ebx, eax
0x140021e32  test    eax, eax
0x140021e34  js      short loc_140021EA2
0x140021e36  cmp     dword ptr [rsi+8], 0FFFFFFFFh
0x140021e3a  jz      short loc_140021E65
0x140021e3c  mov     eax, [rsi+8]
0x140021e3f  lea     r9, [rbp+57h+var_68]
0x140021e43  xor     r8d, r8d
0x140021e46  mov     [rbp+57h+var_68], rax
0x140021e4a  mov     edx, 25000004h
0x140021e4f  mov     dword ptr [rsp+0C0h+var_A0], 8
0x140021e57  mov     rcx, rdi
0x140021e5a  call    BcdSetElementDataWithFlags
0x140021e5f  mov     ebx, eax
0x140021e61  test    eax, eax
0x140021e63  js      short loc_140021EA2
0x140021e65  mov     edx, [rsi+10h]
0x140021e68  cmp     edx, 0FFFFFFFEh
0x140021e6b  jz      short loc_140021EA0
0x140021e6d  mov     rcx, [rbp+57h+var_60]
0x140021e71  lea     r8, [rbp+57h+var_50]
0x140021e75  call    BiTranslateBootEntryId
0x140021e7a  test    eax, eax
0x140021e7c  js      short loc_140021EA0
0x140021e7e  lea     r9, [rbp+57h+var_50]
0x140021e82  mov     dword ptr [rsp+0C0h+var_A0], 10h
0x140021e8a  xor     r8d, r8d
0x140021e8d  mov     edx, 24000002h
0x140021e92  mov     rcx, rdi
0x140021e95  call    BcdSetElementDataWithFlags
0x140021e9a  mov     ebx, eax
0x140021e9c  test    eax, eax
0x140021e9e  js      short loc_140021EA2
0x140021ea0  xor     ebx, ebx
0x140021ea2  test    rsi, rsi
0x140021ea5  jz      short loc_140021EBF
0x140021ea7  mov     rcx, gs:60h
0x140021eb0  mov     r8, rsi; P
0x140021eb3  xor     edx, edx; Flags
0x140021eb5  mov     rcx, [rcx+30h]; HeapHandle
0x140021eb9  call    cs:__imp_RtlFreeHeap
0x140021ebf  test    r15, r15
0x140021ec2  jz      short loc_140021EDC
0x140021ec4  mov     rcx, gs:60h
0x140021ecd  mov     r8, r15; P
0x140021ed0  xor     edx, edx; Flags
0x140021ed2  mov     rcx, [rcx+30h]; HeapHandle
0x140021ed6  call    cs:__imp_RtlFreeHeap
0x140021edc  test    r12, r12
0x140021edf  jz      short loc_140021EF9
0x140021ee1  mov     rcx, gs:60h
0x140021eea  mov     r8, r12; P
0x140021eed  xor     edx, edx; Flags
0x140021eef  mov     rcx, [rcx+30h]; HeapHandle
0x140021ef3  call    cs:__imp_RtlFreeHeap
0x140021ef9  test    rdi, rdi
0x140021efc  jz      short loc_140021F13
0x140021efe  mov     rcx, rdi; Handle
0x140021f01  test    ebx, ebx
0x140021f03  jns     short loc_140021F0C
0x140021f05  call    BcdDeleteObject
0x140021f0a  jmp     short loc_140021F17
0x140021f0c  call    BcdCloseObject
0x140021f11  jmp     short loc_140021F29
0x140021f13  test    ebx, ebx
0x140021f15  jns     short loc_140021F29
0x140021f17  mov     r8d, ebx
0x140021f1a  lea     rdx, aBibindefibootm_0; "BiBindEfiBootManager failed %x"
0x140021f21  mov     ecx, r13d
0x140021f24  call    BiLogMessage
0x140021f29  mov     eax, ebx
0x140021f2b  mov     rcx, [rbp+57h+var_40]
0x140021f2f  xor     rcx, rsp; StackCookie
0x140021f32  call    __security_check_cookie
0x140021f37  mov     rbx, [rsp+0C0h+arg_10]
0x140021f3f  add     rsp, 90h
0x140021f46  pop     r15
0x140021f48  pop     r14
0x140021f4a  pop     r13
0x140021f4c  pop     r12
0x140021f4e  pop     rdi
0x140021f4f  pop     rsi
0x140021f50  pop     rbp
0x140021f51  retn
```
