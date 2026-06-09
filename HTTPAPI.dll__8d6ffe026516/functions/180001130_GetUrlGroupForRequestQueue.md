# GetUrlGroupForRequestQueue

- ea: `0x180001130`
- end: `0x1800011e0`
- name: `GetUrlGroupForRequestQueue`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180003d00`

## callees

- `0x180001130`
- `0x180002b40`
- `0x18000a5f0`
- `0x18000b0b8`

## pseudocode

```c
ULONG __fastcall GetUrlGroupForRequestQueue(void *a1, _QWORD *a2)
{
  ULONG result; // eax
  __int64 v4; // rcx
  ULONG v5; // ebx
  int InputBuffer; // [rsp+40h] [rbp-38h] BYREF
  int InputBuffer_4; // [rsp+44h] [rbp-34h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h] BYREF
  __int128 v9; // [rsp+58h] [rbp-20h]

  InputBuffer_4 = 7;
  *a2 = 0;
  InputBuffer = 0;
  v8 = 0;
  v9 = 0;
  result = HttpApiSynchronousDeviceControl(a1, 0x12402Au, &InputBuffer_4, 4u, &v8, 0x20u, &InputBuffer);
  v5 = result;
  if ( !result )
  {
    *a2 = v9;
    if ( (byte_1800126A3 & 4) != 0 )
    {
      WPP_SF_I(v4, 0xAu, (ULONGLONG)WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001130  mov     [rsp+arg_10], rbx
0x180001135  push    rdi
0x180001136  sub     rsp, 70h
0x18000113a  mov     rax, cs:__security_cookie
0x180001141  xor     rax, rsp
0x180001144  mov     [rsp+78h+var_10], rax
0x180001149  xor     eax, eax
0x18000114b  mov     dword ptr [rsp+78h+InputBuffer+4], 7
0x180001153  mov     [rdx], rax
0x180001156  lea     r8, [rsp+78h+InputBuffer+4]; InputBuffer
0x18000115b  mov     dword ptr [rsp+78h+InputBuffer], eax
0x18000115f  xorps   xmm0, xmm0
0x180001162  lea     rax, [rsp+78h+InputBuffer]
0x180001167  mov     rdi, rdx
0x18000116a  mov     [rsp+78h+var_48], rax; __int64
0x18000116f  mov     r9d, 4; InputBufferLength
0x180001175  lea     rax, [rsp+78h+var_30]
0x18000117a  mov     [rsp+78h+var_50], 20h ; ' '; ULONG
0x180001182  mov     edx, 12402Ah; IoControlCode
0x180001187  mov     [rsp+78h+var_58], rax; PVOID
0x18000118c  movups  [rsp+78h+var_30], xmm0
0x180001191  movups  [rsp+78h+var_20], xmm0
0x180001196  call    HttpApiSynchronousDeviceControl
0x18000119b  mov     ebx, eax
0x18000119d  test    eax, eax
0x18000119f  jnz     short loc_1800011C5
0x1800011a1  mov     r9, qword ptr [rsp+78h+var_20]
0x1800011a6  mov     [rdi], r9
0x1800011a9  test    cs:byte_1800126A3, 4
0x1800011b0  jz      short loc_1800011C5
0x1800011b2  mov     edx, 0Ah
0x1800011b7  lea     r8, WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids
0x1800011be  call    WPP_SF_I
0x1800011c3  mov     eax, ebx
0x1800011c5  mov     rcx, [rsp+78h+var_10]
0x1800011ca  xor     rcx, rsp; StackCookie
0x1800011cd  call    __security_check_cookie
0x1800011d2  mov     rbx, [rsp+78h+arg_10]
0x1800011da  add     rsp, 70h
0x1800011de  pop     rdi
0x1800011df  retn
```
