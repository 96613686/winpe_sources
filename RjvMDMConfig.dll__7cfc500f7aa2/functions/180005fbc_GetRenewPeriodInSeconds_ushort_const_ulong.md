# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x180005fbc`
- end: `0x1800060d0`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `276`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004168`

## callees

- `0x180005a38`
- `0x180005fbc`
- `0x180006574`
- `0x180017278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006014`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800060ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800060ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  HKEY v8; // rcx
  bool v9; // zf
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v4 = 3628800;
  v12 = 3628800;
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath(1);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v13) < 0 )
    {
      v7 = 0;
LABEL_10:
      *a2 = v4;
      goto LABEL_11;
    }
    v7 = ULongLongToULong(24LL * v13, &v12);
    if ( v7 >= 0 )
    {
      v7 = ULongLongToULong(60LL * v12, &v12);
      if ( v7 >= 0 )
      {
        v7 = ULongLongToULong(60LL * v12, &v12);
        if ( v7 >= 0 )
        {
          v4 = v12;
          goto LABEL_10;
        }
      }
    }
  }
LABEL_11:
  v8 = hKey;
  v9 = hKey == 0;
  hKey = 0;
  if ( !v9 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005fbc  mov     [rsp-18h+arg_0], rbx
0x180005fc1  mov     [rsp-18h+arg_8], rsi
0x180005fc6  push    rbp
0x180005fc7  push    rdi
0x180005fc8  push    r14
0x180005fca  mov     rbp, rsp
0x180005fcd  sub     rsp, 40h
0x180005fd1  mov     rsi, rdx
0x180005fd4  mov     r14, rcx
0x180005fd7  mov     [rbp+arg_18], 0
0x180005fde  mov     edi, 375F00h
0x180005fe3  mov     [rbp+arg_10], edi
0x180005fe6  mov     [rbp+hKey], 0
0x180005fee  mov     ecx, 1
0x180005ff3  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180005ff8  lea     rcx, [rbp+hKey]
0x180005ffc  mov     [rsp+40h+phkResult], rcx; phkResult
0x180006001  mov     r9d, 20019h; samDesired
0x180006007  xor     r8d, r8d; ulOptions
0x18000600a  mov     rdx, rax; lpSubKey
0x18000600d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006014  call    cs:__imp_RegOpenKeyExW
0x18000601b  nop     dword ptr [rax+rax+00h]
0x180006020  mov     ebx, eax
0x180006022  test    eax, eax
0x180006024  jle     short loc_18000602F
0x180006026  movzx   ebx, ax
0x180006029  or      ebx, 80070000h
0x18000602f  test    ebx, ebx
0x180006031  js      short loc_18000609D
0x180006033  lea     r9, [rbp+arg_18]; unsigned int *
0x180006037  lea     r8, aRenewalperiod; "RenewalPeriod"
0x18000603e  mov     rdx, r14; unsigned __int16 *
0x180006041  mov     rcx, [rbp+hKey]; HKEY
0x180006045  call    ?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18000604a  test    eax, eax
0x18000604c  jns     short loc_180006052
0x18000604e  xor     ebx, ebx
0x180006050  jmp     short loc_18000609B
0x180006052  mov     eax, [rbp+arg_18]
0x180006055  lea     rcx, [rax+rax*2]
0x180006059  shl     rcx, 3; unsigned __int64
0x18000605d  lea     rdx, [rbp+arg_10]; unsigned int *
0x180006061  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180006066  mov     ebx, eax
0x180006068  test    eax, eax
0x18000606a  js      short loc_18000609D
0x18000606c  mov     eax, [rbp+arg_10]
0x18000606f  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180006073  lea     rdx, [rbp+arg_10]; unsigned int *
0x180006077  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000607c  mov     ebx, eax
0x18000607e  test    eax, eax
0x180006080  js      short loc_18000609D
0x180006082  mov     eax, [rbp+arg_10]
0x180006085  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x180006089  lea     rdx, [rbp+arg_10]; unsigned int *
0x18000608d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180006092  mov     ebx, eax
0x180006094  test    eax, eax
0x180006096  js      short loc_18000609D
0x180006098  mov     edi, [rbp+arg_10]
0x18000609b  mov     [rsi], edi
0x18000609d  mov     rcx, [rbp+hKey]; hKey
0x1800060a1  test    rcx, rcx
0x1800060a4  mov     [rbp+hKey], 0
0x1800060ac  jz      short loc_1800060BA
0x1800060ae  call    cs:__imp_RegCloseKey
0x1800060b5  nop     dword ptr [rax+rax+00h]
0x1800060ba  mov     eax, ebx
0x1800060bc  mov     rbx, [rsp+40h+arg_0]
0x1800060c1  mov     rsi, [rsp+40h+arg_8]
0x1800060c6  add     rsp, 40h
0x1800060ca  pop     r14
0x1800060cc  pop     rdi
0x1800060cd  pop     rbp
0x1800060ce  retn
```
