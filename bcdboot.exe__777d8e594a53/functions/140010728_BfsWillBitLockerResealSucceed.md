# BfsWillBitLockerResealSucceed

- ea: `0x140010728`
- end: `0x14001086f`
- name: `BfsWillBitLockerResealSucceed`
- size: `327`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140009fd4`

## callees

- `0x14000e578`
- `0x14000e5c8`
- `0x14000e628`
- `0x140010728`
- `0x140010878`
- `0x1400265fa`
- `0x140027010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14001084b`
- `KERNEL32!FreeLibrary` at `0x14001084b`

## string_xrefs

- `0x1400107a2`: `BfsWillBitLockerResealSucceed: BfspOpenFveApi failed. FveApiFound = %d, HRESULT = [%x]`

## pseudocode

```c
__int64 __fastcall BfsWillBitLockerResealSucceed(unsigned int *a1)
{
  int v2; // ebp
  int v3; // ebx
  int v4; // eax
  int v5; // esi
  unsigned int v6; // ebx
  __int64 v7; // r9
  int v8; // eax
  HMODULE hLibModule[19]; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v11; // [rsp+D0h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+D8h] [rbp+10h] BYREF

  v11 = -1;
  memset_0(hLibModule, 0, 0x80u);
  v2 = LogEnabled;
  v12 = 0;
  if ( !LogEnabled )
    BfspLogInitialize(0);
  if ( !a1 )
  {
    v3 = -2147024809;
LABEL_10:
    BfspLogMessage(4, L"BfsWillBitLockerResealSucceed: Failed. HRESULT = [%x]", (unsigned int)v3);
    goto LABEL_15;
  }
  *a1 = 0;
  v4 = BfspOpenFveApi((__int64)hLibModule, &v12);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(unsigned int *))hLibModule[15])(&v11);
    v3 = v8;
    if ( v8 < 0 )
    {
      BfspLogMessage(
        3,
        L"BfsWillBitLockerResealSucceed: FveGetSecureBootBindingState failed. HRESULT = [%x]",
        (unsigned int)v8);
      goto LABEL_10;
    }
    v7 = v11;
    if ( v11 - 2 <= 1 )
      *a1 = 1;
    v3 = 0;
  }
  else
  {
    v6 = v12;
    BfspLogMessage(
      3,
      L"BfsWillBitLockerResealSucceed: BfspOpenFveApi failed. FveApiFound = %d, HRESULT = [%x]",
      v12,
      (unsigned int)v4);
    v3 = v6 != 0 ? v5 : 0;
    if ( v3 < 0 )
      goto LABEL_10;
    v7 = v11;
  }
  BfspLogMessage(
    2,
    L"BfsWillBitLockerResealSucceed: Succeeded. WillResealSucceed = [%d], BindingState = [%x], HRESULT = [%x]",
    *a1,
    v7,
    v3);
LABEL_15:
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  if ( !v2 )
    BfspLogDestroy();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140010728  mov     rax, rsp
0x14001072b  mov     [rax+18h], rbx
0x14001072f  push    rbp
0x140010730  push    rsi
0x140010731  push    rdi
0x140010732  sub     rsp, 0B0h
0x140010739  mov     rdi, rcx
0x14001073c  mov     dword ptr [rax+8], 0FFFFFFFFh
0x140010743  lea     rcx, [rsp+0C8h+hLibModule]; void *
0x140010748  xor     edx, edx; Val
0x14001074a  mov     r8d, 80h; Size
0x140010750  call    memset_0
0x140010755  mov     ebp, cs:LogEnabled
0x14001075b  mov     [rsp+0C8h+arg_8], 0
0x140010766  test    ebp, ebp
0x140010768  jnz     short loc_140010771
0x14001076a  xor     ecx, ecx
0x14001076c  call    BfspLogInitialize
0x140010771  test    rdi, rdi
0x140010774  jnz     short loc_14001077D
0x140010776  mov     ebx, 80070057h
0x14001077b  jmp     short loc_1400107FA
0x14001077d  lea     rdx, [rsp+0C8h+arg_8]
0x140010785  mov     dword ptr [rdi], 0
0x14001078b  lea     rcx, [rsp+0C8h+hLibModule]
0x140010790  call    BfspOpenFveApi
0x140010795  mov     esi, eax
0x140010797  test    eax, eax
0x140010799  jns     short loc_1400107CB
0x14001079b  mov     ebx, [rsp+0C8h+arg_8]
0x1400107a2  lea     rdx, aBfswillbitlock_0; "BfsWillBitLockerResealSucceed: BfspOpen"...
0x1400107a9  mov     r8d, ebx
0x1400107ac  mov     r9d, eax
0x1400107af  mov     ecx, 3
0x1400107b4  call    BfspLogMessage
0x1400107b9  neg     ebx
0x1400107bb  sbb     ebx, ebx
0x1400107bd  and     ebx, esi
0x1400107bf  jl      short loc_1400107FA
0x1400107c1  mov     r9d, [rsp+0C8h+arg_0]
0x1400107c9  jmp     short loc_140010829
0x1400107cb  mov     rax, [rsp+0C8h+var_20]
0x1400107d3  lea     rcx, [rsp+0C8h+arg_0]
0x1400107db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107e0  mov     ebx, eax
0x1400107e2  test    eax, eax
0x1400107e4  jns     short loc_140010810
0x1400107e6  mov     r8d, eax
0x1400107e9  lea     rdx, aBfswillbitlock; "BfsWillBitLockerResealSucceed: FveGetSe"...
0x1400107f0  mov     ecx, 3
0x1400107f5  call    BfspLogMessage
0x1400107fa  mov     r8d, ebx
0x1400107fd  lea     rdx, aBfswillbitlock_1; "BfsWillBitLockerResealSucceed: Failed. "...
0x140010804  mov     ecx, 4
0x140010809  call    BfspLogMessage
0x14001080e  jmp     short loc_140010841
0x140010810  mov     r9d, [rsp+0C8h+arg_0]
0x140010818  lea     eax, [r9-2]
0x14001081c  cmp     eax, 1
0x14001081f  ja      short loc_140010827
0x140010821  mov     dword ptr [rdi], 1
0x140010827  xor     ebx, ebx
0x140010829  mov     r8d, [rdi]
0x14001082c  lea     rdx, aBfswillbitlock_2; "BfsWillBitLockerResealSucceed: Succeede"...
0x140010833  mov     ecx, 2
0x140010838  mov     [rsp+0C8h+var_A8], ebx
0x14001083c  call    BfspLogMessage
0x140010841  mov     rcx, [rsp+0C8h+hLibModule]; hLibModule
0x140010846  test    rcx, rcx
0x140010849  jz      short loc_140010851
0x14001084b  call    cs:__imp_FreeLibrary
0x140010851  test    ebp, ebp
0x140010853  jnz     short loc_14001085A
0x140010855  call    BfspLogDestroy
0x14001085a  mov     eax, ebx
0x14001085c  mov     rbx, [rsp+0C8h+arg_10]
0x140010864  add     rsp, 0B0h
0x14001086b  pop     rdi
0x14001086c  pop     rsi
0x14001086d  pop     rbp
0x14001086e  retn
```
