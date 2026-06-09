# std::function<long (DiagHubCommon::AutoEvent const &,void *)>::operator=(std::function<long (DiagHubCommon::AutoEvent const &,void *)> const &)

- ea: `0x140008ca8`
- end: `0x140008e76`
- name: `??4?$function@$$A6AJAEBVAutoEvent@DiagHubCommon@@PEAX@Z@std@@QEAAAEAV01@AEBV01@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008b94`

## callees

- `0x140008ca8`
- `0x1400137e0`
- `0x140014c70`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall std::function<long (DiagHubCommon::AutoEvent const &,void *)>::operator=(__int64 a1, __int64 a2)
{
  _BYTE *v3; // r8
  __int64 (__fastcall ***v4)(_QWORD, _BYTE *); // rcx
  _BYTE *v5; // rcx
  _BYTE *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rcx
  _BYTE v10[56]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE *v11; // [rsp+58h] [rbp-1h]
  _BYTE v12[56]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v13; // [rsp+98h] [rbp+3Fh]

  v3 = 0;
  v11 = 0;
  v4 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a2 + 56);
  if ( v4 )
  {
    v3 = (_BYTE *)(**v4)(v4, v10);
    v11 = v3;
  }
  v5 = v3;
  if ( v3 != v10 && *(_QWORD *)(a1 + 56) != a1 )
  {
    v3 = *(_BYTE **)(a1 + 56);
    v11 = v3;
    *(_QWORD *)(a1 + 56) = v5;
    goto LABEL_26;
  }
  v6 = 0;
  v13 = 0;
  if ( v3 )
  {
    if ( v3 == v10 )
    {
      v6 = (_BYTE *)(*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v3 + 8LL))(v3, v12);
      v13 = v6;
      v3 = v11;
      if ( !v11 )
        goto LABEL_12;
      LOBYTE(a2) = v11 != v10;
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v11 + 32LL))(v11, a2);
      v6 = v13;
    }
    else
    {
      v6 = v3;
      v13 = v3;
    }
    v3 = 0;
    v11 = 0;
  }
LABEL_12:
  v7 = *(_QWORD *)(a1 + 56);
  if ( !v7 )
    goto LABEL_19;
  if ( v7 == a1 )
  {
    v3 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v7 + 8LL))(v7, v10);
    v11 = v3;
    v8 = *(_QWORD *)(a1 + 56);
    if ( !v8 )
    {
      v6 = v13;
      goto LABEL_19;
    }
    LOBYTE(a2) = v8 != a1;
    (*(void (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v8 + 32LL))(v8, a2, v3);
    v3 = v11;
    v6 = v13;
  }
  else
  {
    v3 = *(_BYTE **)(a1 + 56);
    v11 = v3;
  }
  *(_QWORD *)(a1 + 56) = 0;
LABEL_19:
  if ( !v6 )
    goto LABEL_26;
  if ( v6 == v12 )
  {
    *(_QWORD *)(a1 + 56) = (*(__int64 (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v6 + 8LL))(v6, a1);
    if ( !v13 )
    {
      v3 = v11;
      goto LABEL_26;
    }
    LOBYTE(a2) = v13 != v12;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v13 + 32LL))(v13, a2);
    v3 = v11;
  }
  else
  {
    *(_QWORD *)(a1 + 56) = v6;
  }
  v13 = 0;
LABEL_26:
  if ( v3 )
  {
    LOBYTE(a2) = v3 != v10;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
  }
  return a1;
}

```

## disassembly

```asm
0x140008ca8  mov     [rsp-8+arg_10], rbx
0x140008cad  push    rbp
0x140008cae  lea     rbp, [rsp-57h]
0x140008cb3  sub     rsp, 0B0h
0x140008cba  mov     rax, cs:__security_cookie
0x140008cc1  xor     rax, rsp
0x140008cc4  mov     [rbp+57h+var_10], rax
0x140008cc8  mov     rbx, rcx
0x140008ccb  xor     r8d, r8d
0x140008cce  mov     [rbp+57h+var_58], r8
0x140008cd2  mov     rcx, [rdx+38h]
0x140008cd6  test    rcx, rcx
0x140008cd9  jz      short loc_140008CF2
0x140008cdb  mov     rax, [rcx]
0x140008cde  lea     rdx, [rbp+57h+var_90]
0x140008ce2  mov     rax, [rax]
0x140008ce5  call    cs:__guard_dispatch_icall_fptr
0x140008ceb  mov     r8, rax
0x140008cee  mov     [rbp+57h+var_58], rax
0x140008cf2  mov     rcx, r8
0x140008cf5  lea     rax, [rbp+57h+var_90]
0x140008cf9  cmp     r8, rax
0x140008cfc  jz      short loc_140008D15
0x140008cfe  cmp     [rbx+38h], rbx
0x140008d02  jz      short loc_140008D15
0x140008d04  mov     r8, [rbx+38h]
0x140008d08  mov     [rbp+57h+var_58], r8
0x140008d0c  mov     [rbx+38h], rcx
0x140008d10  jmp     loc_140008E37
0x140008d15  xor     r9d, r9d
0x140008d18  mov     [rbp+57h+var_18], r9
0x140008d1c  test    rcx, rcx
0x140008d1f  jz      short loc_140008D79
0x140008d21  lea     rax, [rbp+57h+var_90]
0x140008d25  cmp     rcx, rax
0x140008d28  jnz     short loc_140008D6B
0x140008d2a  mov     rax, [r8]
0x140008d2d  lea     rdx, [rbp+57h+var_50]
0x140008d31  mov     rax, [rax+8]
0x140008d35  call    cs:__guard_dispatch_icall_fptr
0x140008d3b  mov     r9, rax
0x140008d3e  mov     [rbp+57h+var_18], rax
0x140008d42  mov     r8, [rbp+57h+var_58]
0x140008d46  test    r8, r8
0x140008d49  jz      short loc_140008D79
0x140008d4b  lea     rax, [rbp+57h+var_90]
0x140008d4f  cmp     r8, rax
0x140008d52  setnz   dl
0x140008d55  mov     rax, [r8]
0x140008d58  mov     rcx, r8
0x140008d5b  mov     rax, [rax+20h]
0x140008d5f  call    cs:__guard_dispatch_icall_fptr
0x140008d65  mov     r9, [rbp+57h+var_18]
0x140008d69  jmp     short loc_140008D72
0x140008d6b  mov     r9, r8
0x140008d6e  mov     [rbp+57h+var_18], r8
0x140008d72  xor     r8d, r8d
0x140008d75  mov     [rbp+57h+var_58], r8
0x140008d79  mov     rcx, [rbx+38h]
0x140008d7d  test    rcx, rcx
0x140008d80  jz      short loc_140008DDA
0x140008d82  cmp     rcx, rbx
0x140008d85  jnz     short loc_140008DCB
0x140008d87  mov     rax, [rcx]
0x140008d8a  lea     rdx, [rbp+57h+var_90]
0x140008d8e  mov     rax, [rax+8]
0x140008d92  call    cs:__guard_dispatch_icall_fptr
0x140008d98  mov     r8, rax
0x140008d9b  mov     [rbp+57h+var_58], rax
0x140008d9f  mov     rcx, [rbx+38h]
0x140008da3  test    rcx, rcx
0x140008da6  jz      short loc_140008DC5
0x140008da8  cmp     rcx, rbx
0x140008dab  setnz   dl
0x140008dae  mov     rax, [rcx]
0x140008db1  mov     rax, [rax+20h]
0x140008db5  call    cs:__guard_dispatch_icall_fptr
0x140008dbb  mov     r8, [rbp+57h+var_58]
0x140008dbf  mov     r9, [rbp+57h+var_18]
0x140008dc3  jmp     short loc_140008DD2
0x140008dc5  mov     r9, [rbp+57h+var_18]
0x140008dc9  jmp     short loc_140008DDA
0x140008dcb  mov     r8, rcx
0x140008dce  mov     [rbp+57h+var_58], rcx
0x140008dd2  mov     qword ptr [rbx+38h], 0
0x140008dda  test    r9, r9
0x140008ddd  jz      short loc_140008E37
0x140008ddf  lea     rax, [rbp+57h+var_50]
0x140008de3  cmp     r9, rax
0x140008de6  jnz     short loc_140008E2B
0x140008de8  mov     rax, [r9]
0x140008deb  mov     rdx, rbx
0x140008dee  mov     rcx, r9
0x140008df1  mov     rax, [rax+8]
0x140008df5  call    cs:__guard_dispatch_icall_fptr
0x140008dfb  mov     [rbx+38h], rax
0x140008dff  mov     rcx, [rbp+57h+var_18]
0x140008e03  test    rcx, rcx
0x140008e06  jz      short loc_140008E25
0x140008e08  lea     rax, [rbp+57h+var_50]
0x140008e0c  cmp     rcx, rax
0x140008e0f  setnz   dl
0x140008e12  mov     rax, [rcx]
0x140008e15  mov     rax, [rax+20h]
0x140008e19  call    cs:__guard_dispatch_icall_fptr
0x140008e1f  mov     r8, [rbp+57h+var_58]
0x140008e23  jmp     short loc_140008E2F
0x140008e25  mov     r8, [rbp+57h+var_58]
0x140008e29  jmp     short loc_140008E37
0x140008e2b  mov     [rbx+38h], r9
0x140008e2f  mov     [rbp+57h+var_18], 0
0x140008e37  test    r8, r8
0x140008e3a  jz      short loc_140008E56
0x140008e3c  lea     rax, [rbp+57h+var_90]
0x140008e40  cmp     r8, rax
0x140008e43  setnz   dl
0x140008e46  mov     rcx, [r8]
0x140008e49  mov     rax, [rcx+20h]
0x140008e4d  mov     rcx, r8
0x140008e50  call    cs:__guard_dispatch_icall_fptr
0x140008e56  mov     rax, rbx
0x140008e59  mov     rcx, [rbp+57h+var_10]
0x140008e5d  xor     rcx, rsp; StackCookie
0x140008e60  call    __security_check_cookie
0x140008e65  mov     rbx, [rsp+0B0h+arg_10]
0x140008e6d  add     rsp, 0B0h
0x140008e74  pop     rbp
0x140008e75  retn
```
