# CFlightingAdmin::GetFlightSigningBcdSettings(int *,int *)

- ea: `0x1800925c4`
- end: `0x180092714`
- name: `?GetFlightSigningBcdSettings@CFlightingAdmin@@SAHPEAH0@Z`
- size: `336`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800b9d90`

## callees

- `0x180004b80`
- `0x1800925c4`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180092684`
- `ntdll!NtQuerySystemInformation` at `0x180092684`
- `bcd!BcdCloseStore` at `0x1800926eb`
- `bcd!BcdCloseStore` at `0x1800926eb`
- `bcd!BcdCloseObject` at `0x1800926cd`
- `bcd!BcdCloseObject` at `0x1800926dc`
- `bcd!BcdCloseObject` at `0x1800926cd`
- `bcd!BcdCloseObject` at `0x1800926dc`
- `bcd!BcdGetElementData` at `0x180092669`
- `bcd!BcdGetElementData` at `0x1800926bc`
- `bcd!BcdGetElementData` at `0x180092669`
- `bcd!BcdGetElementData` at `0x1800926bc`
- `bcd!BcdOpenStore` at `0x180092625`
- `bcd!BcdOpenStore` at `0x180092625`
- `bcd!BcdOpenObject` at `0x180092644`
- `bcd!BcdOpenObject` at `0x18009269c`
- `bcd!BcdOpenObject` at `0x180092644`
- `bcd!BcdOpenObject` at `0x18009269c`

## pseudocode

```c
_BOOL8 __fastcall CFlightingAdmin::GetFlightSigningBcdSettings(int *a1, int *a2)
{
  NTSTATUS v4; // ebx
  int v6; // [rsp+20h] [rbp-50h] BYREF
  __int64 v7; // [rsp+28h] [rbp-48h] BYREF
  __int64 v8; // [rsp+30h] [rbp-40h] BYREF
  __int64 v9; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SystemInformation[2]; // [rsp+40h] [rbp-30h] BYREF

  *a2 = 0;
  *a1 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v6 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v4 = BcdOpenStore(0, 0, &v7);
  if ( v4 >= 0 )
  {
    v4 = BcdOpenObject(v7, &GUID_WINDOWS_BOOTMGR, &v8);
    if ( v4 >= 0 )
    {
      v6 = 4;
      v4 = ((__int64 (__fastcall *)(__int64, __int64, int *, int *))BcdGetElementData)(v8, 369098878, a2, &v6);
      if ( v4 >= 0 )
      {
        v4 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, 0);
        if ( v4 >= 0 )
        {
          v4 = BcdOpenObject(v7, SystemInformation, &v9);
          if ( v4 >= 0 )
          {
            v6 = 4;
            v4 = ((__int64 (__fastcall *)(__int64, __int64, int *, int *))BcdGetElementData)(v9, 369098878, a1, &v6);
          }
        }
      }
    }
  }
  if ( v8 )
    BcdCloseObject();
  if ( v9 )
    BcdCloseObject();
  if ( v7 )
    BcdCloseStore();
  return v4 >= 0;
}

```

## disassembly

```asm
0x1800925c4  mov     [rsp-18h+arg_10], rbx
0x1800925c9  push    rbp
0x1800925ca  push    rsi
0x1800925cb  push    rdi
0x1800925cc  mov     rbp, rsp
0x1800925cf  sub     rsp, 70h
0x1800925d3  mov     rax, cs:__security_cookie
0x1800925da  xor     rax, rsp
0x1800925dd  mov     [rbp+var_10], rax
0x1800925e1  mov     dword ptr [rdx], 0
0x1800925e7  lea     r8, [rbp+var_48]
0x1800925eb  xorps   xmm0, xmm0
0x1800925ee  mov     dword ptr [rcx], 0
0x1800925f4  mov     rdi, rdx
0x1800925f7  mov     [rbp+var_48], 0
0x1800925ff  mov     rsi, rcx
0x180092602  mov     [rbp+var_40], 0
0x18009260a  xor     ecx, ecx
0x18009260c  mov     [rbp+var_38], 0
0x180092614  xor     edx, edx
0x180092616  mov     [rbp+var_50], 0
0x18009261d  movups  [rbp+SystemInformation], xmm0
0x180092621  movups  [rbp+var_20], xmm0
0x180092625  call    cs:__imp_BcdOpenStore
0x18009262b  mov     ebx, eax
0x18009262d  test    eax, eax
0x18009262f  js      loc_1800926C4
0x180092635  mov     rcx, [rbp+var_48]
0x180092639  lea     r8, [rbp+var_40]
0x18009263d  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180092644  call    cs:__imp_BcdOpenObject
0x18009264a  mov     ebx, eax
0x18009264c  test    eax, eax
0x18009264e  js      short loc_1800926C4
0x180092650  mov     rcx, [rbp+var_40]
0x180092654  lea     r9, [rbp+var_50]
0x180092658  mov     r8, rdi
0x18009265b  mov     [rbp+var_50], 4
0x180092662  mov     edi, 1600007Eh
0x180092667  mov     edx, edi
0x180092669  call    cs:__imp_BcdGetElementData
0x18009266f  mov     ebx, eax
0x180092671  test    eax, eax
0x180092673  js      short loc_1800926C4
0x180092675  xor     r9d, r9d; ReturnLength
0x180092678  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18009267c  lea     r8d, [r9+20h]; SystemInformationLength
0x180092680  lea     ecx, [r9+5Ah]; SystemInformationClass
0x180092684  call    cs:__imp_NtQuerySystemInformation
0x18009268a  mov     ebx, eax
0x18009268c  test    eax, eax
0x18009268e  js      short loc_1800926C4
0x180092690  mov     rcx, [rbp+var_48]
0x180092694  lea     r8, [rbp+var_38]
0x180092698  lea     rdx, [rbp+SystemInformation]
0x18009269c  call    cs:__imp_BcdOpenObject
0x1800926a2  mov     ebx, eax
0x1800926a4  test    eax, eax
0x1800926a6  js      short loc_1800926C4
0x1800926a8  mov     rcx, [rbp+var_38]
0x1800926ac  lea     r9, [rbp+var_50]
0x1800926b0  mov     r8, rsi
0x1800926b3  mov     [rbp+var_50], 4
0x1800926ba  mov     edx, edi
0x1800926bc  call    cs:__imp_BcdGetElementData
0x1800926c2  mov     ebx, eax
0x1800926c4  mov     rcx, [rbp+var_40]
0x1800926c8  test    rcx, rcx
0x1800926cb  jz      short loc_1800926D3
0x1800926cd  call    cs:__imp_BcdCloseObject
0x1800926d3  mov     rcx, [rbp+var_38]
0x1800926d7  test    rcx, rcx
0x1800926da  jz      short loc_1800926E2
0x1800926dc  call    cs:__imp_BcdCloseObject
0x1800926e2  mov     rcx, [rbp+var_48]
0x1800926e6  test    rcx, rcx
0x1800926e9  jz      short loc_1800926F1
0x1800926eb  call    cs:__imp_BcdCloseStore
0x1800926f1  not     ebx
0x1800926f3  shr     ebx, 1Fh
0x1800926f6  mov     eax, ebx
0x1800926f8  mov     rcx, [rbp+var_10]
0x1800926fc  xor     rcx, rsp; StackCookie
0x1800926ff  call    __security_check_cookie
0x180092704  mov     rbx, [rsp+70h+arg_10]
0x18009270c  add     rsp, 70h
0x180092710  pop     rdi
0x180092711  pop     rsi
0x180092712  pop     rbp
0x180092713  retn
```
