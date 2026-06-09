# WdfRequestCompleteOrForwardStatusIoctlRequest

- ea: `0x14000b0ac`
- end: `0x14000b268`
- name: `WdfRequestCompleteOrForwardStatusIoctlRequest`
- size: `444`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007b28`
- `0x14000828c`
- `0x1400083b8`
- `0x1400084e4`
- `0x14002c41c`

## callees

- `0x14000ae30`
- `0x14000b0ac`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000b1eb`
- `ntoskrnl!RtlCompareMemory` at `0x14000b1eb`

## pseudocode

```c
__int64 __fastcall WdfRequestCompleteOrForwardStatusIoctlRequest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *Source2)
{
  __int64 v9; // r15
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 (__fastcall *v13)(PWDF_DRIVER_GLOBALS, __int64, __int64); // rax
  __int64 result; // rax
  int v15; // eax
  _DWORD *v16; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v17; // [rsp+38h] [rbp-40h] BYREF

  v16 = 0;
  v17 = 0;
  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2216))(WdfDriverGlobals, a1);
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _DWORD **, _QWORD))(WdfFunctions_01015 + 2152))(
          WdfDriverGlobals,
          a1,
          4,
          &v16,
          0);
  v11 = (unsigned int)v10;
  v12 = a1;
  if ( v10 < 0 )
  {
    v13 = *(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104);
    return v13(WdfDriverGlobals, v12, v11);
  }
  v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _DWORD **, _QWORD))(WdfFunctions_01015 + 2160))(
          WdfDriverGlobals,
          a1,
          4,
          &v17,
          0);
  v11 = (unsigned int)v15;
  if ( v15 < 0 )
    goto LABEL_5;
  if ( *v16 )
    goto LABEL_14;
  if ( (int)WdfIoQueueFindIoctlRequest(a2, v9, a3, 0) >= 0 )
  {
    v11 = 2147483665LL;
    v13 = *(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104);
    goto LABEL_6;
  }
  if ( *v16 || RtlCompareMemory(a4, Source2, 4u) != 4 )
  {
LABEL_14:
    *Source2 = *a4;
    *v17 = *a4;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01015 + 2120))(
             WdfDriverGlobals,
             a1,
             0,
             4);
  }
  else
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2248))(
               WdfDriverGlobals,
               a1,
               a2);
    v11 = (unsigned int)result;
    if ( (int)result < 0 )
    {
LABEL_5:
      v13 = *(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104);
LABEL_6:
      v12 = a1;
      return v13(WdfDriverGlobals, v12, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b0ac  push    rbx
0x14000b0ae  push    rbp
0x14000b0af  push    rsi
0x14000b0b0  push    rdi
0x14000b0b1  push    r13
0x14000b0b3  push    r14
0x14000b0b5  push    r15
0x14000b0b7  sub     rsp, 40h
0x14000b0bb  mov     rax, cs:WdfFunctions_01015
0x14000b0c2  mov     rbp, rdx
0x14000b0c5  mov     rbx, rcx
0x14000b0c8  mov     [rsp+78h+var_48], 0
0x14000b0d1  mov     [rsp+78h+var_40], 0
0x14000b0da  mov     rdx, rcx
0x14000b0dd  mov     rcx, cs:WdfDriverGlobals
0x14000b0e4  mov     rsi, r9
0x14000b0e7  mov     rax, [rax+8A8h]
0x14000b0ee  mov     r14d, r8d
0x14000b0f1  call    _guard_dispatch_icall
0x14000b0f6  mov     r8, cs:WdfFunctions_01015
0x14000b0fd  lea     r9, [rsp+78h+var_48]
0x14000b102  mov     rcx, cs:WdfDriverGlobals
0x14000b109  mov     r15, rax
0x14000b10c  mov     r13d, 4
0x14000b112  mov     [rsp+78h+var_58], 0
0x14000b11b  mov     rdx, rbx
0x14000b11e  mov     rax, [r8+868h]
0x14000b125  mov     r8d, r13d
0x14000b128  call    _guard_dispatch_icall
0x14000b12d  mov     r8d, eax
0x14000b130  mov     rdx, rbx
0x14000b133  test    eax, eax
0x14000b135  jns     short loc_14000B156
0x14000b137  mov     rcx, cs:WdfFunctions_01015
0x14000b13e  mov     rax, [rcx+838h]
0x14000b145  mov     rcx, cs:WdfDriverGlobals
0x14000b14c  call    _guard_dispatch_icall
0x14000b151  jmp     loc_14000B258
0x14000b156  mov     rax, cs:WdfFunctions_01015
0x14000b15d  lea     r9, [rsp+78h+var_40]
0x14000b162  mov     rcx, cs:WdfDriverGlobals
0x14000b169  mov     r8, r13
0x14000b16c  mov     [rsp+78h+var_58], 0
0x14000b175  mov     rax, [rax+870h]
0x14000b17c  call    _guard_dispatch_icall
0x14000b181  mov     r8d, eax
0x14000b184  test    eax, eax
0x14000b186  jns     short loc_14000B19B
0x14000b188  mov     rcx, cs:WdfFunctions_01015
0x14000b18f  mov     rax, [rcx+838h]
0x14000b196  mov     rdx, rbx
0x14000b199  jmp     short loc_14000B145
0x14000b19b  mov     rax, [rsp+78h+var_48]
0x14000b1a0  mov     rdi, [rsp+78h+Source2]
0x14000b1a8  cmp     dword ptr [rax], 0
0x14000b1ab  jnz     short loc_14000B228
0x14000b1ad  xor     r9d, r9d
0x14000b1b0  mov     r8d, r14d
0x14000b1b3  mov     rdx, r15
0x14000b1b6  mov     rcx, rbp
0x14000b1b9  call    WdfIoQueueFindIoctlRequest
0x14000b1be  test    eax, eax
0x14000b1c0  js      short loc_14000B1D8
0x14000b1c2  mov     rax, cs:WdfFunctions_01015
0x14000b1c9  mov     r8d, 80000011h
0x14000b1cf  mov     rax, [rax+838h]
0x14000b1d6  jmp     short loc_14000B196
0x14000b1d8  mov     rax, [rsp+78h+var_48]
0x14000b1dd  cmp     dword ptr [rax], 0
0x14000b1e0  jnz     short loc_14000B228
0x14000b1e2  mov     r8, r13; Length
0x14000b1e5  mov     rdx, rdi; Source2
0x14000b1e8  mov     rcx, rsi; Source1
0x14000b1eb  call    cs:__imp_RtlCompareMemory
0x14000b1f2  nop     dword ptr [rax+rax+00h]
0x14000b1f7  cmp     rax, r13
0x14000b1fa  jnz     short loc_14000B228
0x14000b1fc  mov     rax, cs:WdfFunctions_01015
0x14000b203  mov     r8, rbp
0x14000b206  mov     rcx, cs:WdfDriverGlobals
0x14000b20d  mov     rdx, rbx
0x14000b210  mov     rax, [rax+8C8h]
0x14000b217  call    _guard_dispatch_icall
0x14000b21c  mov     r8d, eax
0x14000b21f  test    eax, eax
0x14000b221  jns     short loc_14000B258
0x14000b223  jmp     loc_14000B188
0x14000b228  mov     eax, [rsi]
0x14000b22a  mov     r9, r13
0x14000b22d  mov     [rdi], eax
0x14000b22f  xor     r8d, r8d
0x14000b232  mov     rax, [rsp+78h+var_40]
0x14000b237  mov     rdx, rbx
0x14000b23a  mov     ecx, [rsi]
0x14000b23c  mov     [rax], ecx
0x14000b23e  mov     rax, cs:WdfFunctions_01015
0x14000b245  mov     rcx, cs:WdfDriverGlobals
0x14000b24c  mov     rax, [rax+848h]
0x14000b253  call    _guard_dispatch_icall
0x14000b258  add     rsp, 40h
0x14000b25c  pop     r15
0x14000b25e  pop     r14
0x14000b260  pop     r13
0x14000b262  pop     rdi
0x14000b263  pop     rsi
0x14000b264  pop     rbp
0x14000b265  pop     rbx
0x14000b266  retn
```
