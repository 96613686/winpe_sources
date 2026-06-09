# SyncCallThread(void *)

- ea: `0x18001c930`
- end: `0x18001cac1`
- name: `?SyncCallThread@@YAKPEAX@Z`
- size: `401`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18001c7fc`
- `0x18001c930`
- `0x1800543c0`
- `0x18006a010`

## import_xrefs

- `ole32!CoGetClassObject` at `0x18001c98e`
- `ole32!CoGetClassObject` at `0x18001c98e`

## string_xrefs

- `0x18001c9a9`: `SyncCallThread`
- `0x18001ca60`: `SyncCallThread`
- `0x18001c9e0`: `0x%08x CreateInstance failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SyncCallThread(unsigned int *Parameter)
{
  HRESULT ClassObject; // eax
  const char *v3; // r9
  __int64 v4; // r8
  int v5; // edi
  LPVOID *ppv; // [rsp+28h] [rbp-69h]
  __int64 v8; // [rsp+38h] [rbp-59h] BYREF
  LPVOID v9[3]; // [rsp+40h] [rbp-51h] BYREF
  __int128 v10; // [rsp+58h] [rbp-39h] BYREF
  __int128 v11; // [rsp+68h] [rbp-29h] BYREF
  _BYTE v12[94]; // [rsp+78h] [rbp-19h] BYREF
  __int16 v13; // [rsp+D6h] [rbp+45h]

  v9[1] = (LPVOID)-2LL;
  v9[0] = 0;
  v8 = 0;
  ClassObject = CoGetClassObject(&CLSID_MitigationAPIBroker, 4u, 0, &GUID_00000001_0000_0000_c000_000000000046, v9);
  if ( ClassObject < 0 )
  {
    v3 = "0x%08x CoGetClassObject failed";
    v4 = 217;
LABEL_3:
    LODWORD(ppv) = ClassObject;
    AslLogCallPrintf(1, "SyncCallThread", v4, v3, ppv);
    goto LABEL_8;
  }
  ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)v9[0] + 24LL))(
                  v9[0],
                  0,
                  &GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c,
                  &v8);
  if ( ClassObject < 0 )
  {
    v3 = "0x%08x CreateInstance failed";
    v4 = 224;
    goto LABEL_3;
  }
  v10 = xmmword_180072678;
  v11 = *(_OWORD *)Parameter;
  v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int128 *))(*(_QWORD *)v8 + 40LL))(
         v8,
         &v11,
         Parameter[4],
         &v10);
  if ( v5 < 0 )
  {
    memset_0(v12, 0, 0x60u);
    GuidToString(Parameter, v12);
    v13 = 0;
    LODWORD(ppv) = v5;
    AslLogCallPrintf(1, "SyncCallThread", 236, "RunSystemInitiatedTroubleshooter failed, 0x%x, %ws", ppv, v12);
  }
LABEL_8:
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9[0] + 16LL))(v9[0]);
  return 0;
}

```

## disassembly

```asm
0x18001c930  mov     rax, rsp
0x18001c933  push    rbp
0x18001c934  lea     rbp, [rax-5Fh]
0x18001c938  sub     rsp, 0E0h
0x18001c93f  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18001c947  mov     [rax+10h], rbx
0x18001c94b  mov     [rax+18h], rdi
0x18001c94f  mov     rax, cs:__security_cookie
0x18001c956  xor     rax, rsp
0x18001c959  mov     [rbp+57h+var_10], rax
0x18001c95d  mov     rbx, rcx
0x18001c960  mov     [rbp+57h+var_A8], 0
0x18001c968  mov     [rbp+57h+var_B0], 0
0x18001c970  lea     rax, [rbp+57h+var_A8]
0x18001c974  mov     [rsp+0E0h+ppv], rax; ppv
0x18001c979  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18001c980  xor     r8d, r8d; pvReserved
0x18001c983  lea     edx, [r8+4]; dwClsContext
0x18001c987  lea     rcx, CLSID_MitigationAPIBroker; rclsid
0x18001c98e  call    cs:__imp_CoGetClassObject
0x18001c994  test    eax, eax
0x18001c996  jns     short loc_18001C9BF
0x18001c998  lea     r9, a0x08xCogetclas; "0x%08x CoGetClassObject failed"
0x18001c99f  mov     r8d, 0D9h
0x18001c9a5  mov     dword ptr [rsp+0E0h+ppv], eax
0x18001c9a9  lea     rdx, aSynccallthread; "SyncCallThread"
0x18001c9b0  mov     ecx, 1
0x18001c9b5  call    AslLogCallPrintf
0x18001c9ba  jmp     loc_18001CA72
0x18001c9bf  mov     rcx, [rbp+57h+var_A8]
0x18001c9c3  mov     rax, [rcx]
0x18001c9c6  lea     r9, [rbp+57h+var_B0]
0x18001c9ca  lea     r8, _GUID_39dfff64_6bee_4c8d_8575_b1a834f6bd2c
0x18001c9d1  xor     edx, edx
0x18001c9d3  mov     rax, [rax+18h]
0x18001c9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9dc  test    eax, eax
0x18001c9de  jns     short loc_18001C9EF
0x18001c9e0  lea     r9, a0x08xCreateins; "0x%08x CreateInstance failed"
0x18001c9e7  mov     r8d, 0E0h
0x18001c9ed  jmp     short loc_18001C9A5
0x18001c9ef  mov     rcx, [rbp+57h+var_B0]
0x18001c9f3  movups  xmm0, cs:xmmword_180072678
0x18001c9fa  movdqu  [rbp+57h+var_90], xmm0
0x18001c9ff  movups  xmm0, xmmword ptr [rbx]
0x18001ca02  movdqu  [rbp+57h+var_80], xmm0
0x18001ca07  mov     rax, [rcx]
0x18001ca0a  lea     r9, [rbp+57h+var_90]
0x18001ca0e  mov     r8d, [rbx+10h]
0x18001ca12  lea     rdx, [rbp+57h+var_80]
0x18001ca16  mov     rax, [rax+28h]
0x18001ca1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca1f  mov     edi, eax
0x18001ca21  test    eax, eax
0x18001ca23  jns     short loc_18001CA72
0x18001ca25  xor     edx, edx; Val
0x18001ca27  lea     r8d, [rdx+60h]; Size
0x18001ca2b  lea     rcx, [rbp+57h+var_70]; void *
0x18001ca2f  call    memset_0
0x18001ca34  lea     rdx, [rbp+57h+var_70]
0x18001ca38  mov     rcx, rbx
0x18001ca3b  call    GuidToString
0x18001ca40  xor     ecx, ecx
0x18001ca42  mov     [rbp+57h+var_12], cx
0x18001ca46  lea     rax, [rbp+57h+var_70]
0x18001ca4a  mov     [rsp+0E0h+var_B8], rax
0x18001ca4f  mov     dword ptr [rsp+0E0h+ppv], edi
0x18001ca53  lea     r9, aRunsysteminiti; "RunSystemInitiatedTroubleshooter failed"...
0x18001ca5a  mov     r8d, 0ECh
0x18001ca60  lea     rdx, aSynccallthread; "SyncCallThread"
0x18001ca67  mov     ecx, 1
0x18001ca6c  call    AslLogCallPrintf
0x18001ca71  nop
0x18001ca72  mov     rcx, [rbp+57h+var_B0]
0x18001ca76  test    rcx, rcx
0x18001ca79  jz      short loc_18001CA88
0x18001ca7b  mov     rax, [rcx]
0x18001ca7e  mov     rax, [rax+10h]
0x18001ca82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca87  nop
0x18001ca88  mov     rcx, [rbp+57h+var_A8]
0x18001ca8c  test    rcx, rcx
0x18001ca8f  jz      short loc_18001CA9E
0x18001ca91  mov     rax, [rcx]
0x18001ca94  mov     rax, [rax+10h]
0x18001ca98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca9d  nop
0x18001ca9e  xor     eax, eax
0x18001caa0  mov     rcx, [rbp+57h+var_10]
0x18001caa4  xor     rcx, rsp; StackCookie
0x18001caa7  call    __security_check_cookie
0x18001caac  lea     r11, [rsp+0E0h+var_s0]
0x18001cab4  mov     rbx, [r11+18h]
0x18001cab8  mov     rdi, [r11+20h]
0x18001cabc  mov     rsp, r11
0x18001cabf  pop     rbp
0x18001cac0  retn
```
