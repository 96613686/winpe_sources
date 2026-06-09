# std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NetSetup2::Property>>>,_lambda_e5393873e9692dbe1f8b07ffef5db8a9_>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NetSetup2::Property>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NetSetup2::Property>>>,_lambda_e5393873e9692dbe1f8b07ffef5db8a9_)

- ea: `0x18001cd80`
- end: `0x18001cee0`
- name: `??$remove_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VProperty@NetSetup2@@@std@@@std@@@std@@V_lambda_e5393873e9692dbe1f8b07ffef5db8a9_@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VProperty@NetSetup2@@@std@@@std@@@0@V10@V10@V_lambda_e5393873e9692dbe1f8b07ffef5db8a9_@@@Z`
- size: `352`
- prototype: `__int128 **(__int128 **, __int128 *, __int128 *, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180020384`

## callees

- `0x1800027c0`
- `0x180008d94`
- `0x18000d974`
- `0x18001c70c`
- `0x18001cd80`
- `0x18002b9a0`
- `0x18002bdfc`
- `0x18002c728`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int128 **std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<NetSetup2::Property>>>,_lambda_e5393873e9692dbe1f8b07ffef5db8a9_>(
        __int128 **a1,
        __int128 *a2,
        __int128 *a3,
        ...)
{
  __int64 v3; // rsi
  __int64 v7; // rdi
  __int128 *v8; // r8
  struct Property v9; // rax
  bool Boolean; // r14
  __int128 *i; // r14
  struct Property v12; // rax
  bool v13; // di
  __int64 v15; // [rsp+28h] [rbp-39h] BYREF
  __int64 v16; // [rsp+30h] [rbp-31h] BYREF
  int v17; // [rsp+38h] [rbp-29h]
  __int128 v18; // [rsp+3Ch] [rbp-25h]
  _BYTE v19[8]; // [rsp+50h] [rbp-11h] BYREF
  _BYTE v20[24]; // [rsp+58h] [rbp-9h] BYREF
  _BYTE v21[24]; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+7Fh] BYREF
  va_list va; // [rsp+E0h] [rbp+7Fh]
  va_list va1; // [rsp+E8h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v22 = va_arg(va1, _QWORD);
  v3 = v22;
  v7 = *(_QWORD *)std::_Pass_fn<_lambda_a12fe479f797c3185504a0a07d9bde97_>(v19, (__int64 *)va);
  if ( a2 != v8 )
  {
    do
    {
      v15 = v7;
      v16 = 0;
      v17 = (*((_DWORD *)a2 + 4) << 16) | 0xA;
      v18 = *a2;
      v9.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                    (NetSetup2::ActiveObject *)&v15,
                    (const struct _NETSETUPPROPKEY *)v20).lpVtbl;
      Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)v9.lpVtbl);
      std::vector<unsigned char>::_Tidy(v21);
      std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v16);
      if ( Boolean )
        break;
      a2 += 3;
    }
    while ( a2 != a3 );
  }
  if ( a2 != a3 )
  {
    for ( i = a2 + 3; i != a3; i += 3 )
    {
      v15 = v3;
      v16 = 0;
      v17 = (*((_DWORD *)i + 4) << 16) | 0xA;
      v18 = *i;
      v12.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                     (NetSetup2::ActiveObject *)&v15,
                     (const struct _NETSETUPPROPKEY *)v20).lpVtbl;
      v13 = NetSetup2::Property::GetBoolean((NetSetup2::Property *)v12.lpVtbl);
      std::vector<unsigned char>::_Tidy(v21);
      std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v16);
      if ( !v13 )
      {
        NetSetup2::Property::operator=(a2, i);
        a2 += 3;
      }
    }
  }
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x18001cd80  mov     rax, rsp
0x18001cd83  mov     [rax+10h], rbx
0x18001cd87  mov     [rax+18h], rsi
0x18001cd8b  mov     [rax+20h], r9
0x18001cd8f  push    rbp
0x18001cd90  push    rdi
0x18001cd91  push    r12
0x18001cd93  push    r14
0x18001cd95  push    r15
0x18001cd97  lea     rbp, [rax-5Fh]
0x18001cd9b  sub     rsp, 90h
0x18001cda2  mov     rax, cs:__security_cookie
0x18001cda9  xor     rax, rsp
0x18001cdac  mov     [rbp+57h+var_30], rax
0x18001cdb0  mov     rsi, r9
0x18001cdb3  mov     rbx, r8
0x18001cdb6  mov     r15, rdx
0x18001cdb9  mov     r12, rcx
0x18001cdbc  lea     rdx, [rbp+57h+arg_18]
0x18001cdc0  lea     rcx, [rbp+57h+var_68]
0x18001cdc4  call    ??$_Pass_fn@V_lambda_a12fe479f797c3185504a0a07d9bde97_@@@std@@YA?A_PAEAV_lambda_a12fe479f797c3185504a0a07d9bde97_@@@Z
0x18001cdc9  mov     rdi, [rax]
0x18001cdcc  cmp     r15, r8
0x18001cdcf  jz      short loc_18001CE34
0x18001cdd1  mov     [rbp+57h+var_90], rdi
0x18001cdd5  mov     [rbp+57h+var_88], 0
0x18001cddd  mov     eax, [r15+10h]
0x18001cde1  shl     eax, 10h
0x18001cde4  or      eax, 0Ah
0x18001cde7  mov     [rbp+57h+var_80], eax
0x18001cdea  movups  xmm0, xmmword ptr [r15]
0x18001cdee  movdqu  [rbp+57h+var_7C], xmm0
0x18001cdf3  lea     r8, NETSETUPPKEY_Reflection_IsReadOnly
0x18001cdfa  lea     rdx, [rbp+57h+var_60]; struct _NETSETUPPROPKEY *
0x18001cdfe  lea     rcx, [rbp+57h+var_90]; this
0x18001ce02  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18001ce07  nop
0x18001ce08  mov     rcx, rax; this
0x18001ce0b  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18001ce10  mov     r14b, al
0x18001ce13  lea     rcx, [rbp+57h+var_48]
0x18001ce17  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001ce1c  nop
0x18001ce1d  lea     rcx, [rbp+57h+var_88]
0x18001ce21  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001ce26  test    r14b, r14b
0x18001ce29  jnz     short loc_18001CE34
0x18001ce2b  add     r15, 30h ; '0'
0x18001ce2f  cmp     r15, rbx
0x18001ce32  jnz     short loc_18001CDD1
0x18001ce34  cmp     r15, rbx
0x18001ce37  jz      short loc_18001CEB1
0x18001ce39  lea     r14, [r15+30h]
0x18001ce3d  jmp     short loc_18001CEAC
0x18001ce3f  mov     [rbp+57h+var_90], rsi
0x18001ce43  mov     [rbp+57h+var_88], 0
0x18001ce4b  mov     eax, [r14+10h]
0x18001ce4f  shl     eax, 10h
0x18001ce52  or      eax, 0Ah
0x18001ce55  mov     [rbp+57h+var_80], eax
0x18001ce58  movups  xmm0, xmmword ptr [r14]
0x18001ce5c  movdqu  [rbp+57h+var_7C], xmm0
0x18001ce61  lea     r8, NETSETUPPKEY_Reflection_IsReadOnly
0x18001ce68  lea     rdx, [rbp+57h+var_60]; struct _NETSETUPPROPKEY *
0x18001ce6c  lea     rcx, [rbp+57h+var_90]; this
0x18001ce70  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18001ce75  nop
0x18001ce76  mov     rcx, rax; this
0x18001ce79  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18001ce7e  mov     dil, al
0x18001ce81  lea     rcx, [rbp+57h+var_48]
0x18001ce85  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001ce8a  nop
0x18001ce8b  lea     rcx, [rbp+57h+var_88]
0x18001ce8f  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001ce94  test    dil, dil
0x18001ce97  jnz     short loc_18001CEA8
0x18001ce99  mov     rdx, r14
0x18001ce9c  mov     rcx, r15
0x18001ce9f  call    ??4Property@NetSetup2@@QEAAAEAV01@$$QEAV01@@Z; NetSetup2::Property::operator=(NetSetup2::Property &&)
0x18001cea4  add     r15, 30h ; '0'
0x18001cea8  add     r14, 30h ; '0'
0x18001ceac  cmp     r14, rbx
0x18001ceaf  jnz     short loc_18001CE3F
0x18001ceb1  mov     [r12], r15
0x18001ceb5  mov     rax, r12
0x18001ceb8  mov     rcx, [rbp+57h+var_30]
0x18001cebc  xor     rcx, rsp; StackCookie
0x18001cebf  call    __security_check_cookie
0x18001cec4  lea     r11, [rsp+0B0h+var_20]
0x18001cecc  mov     rbx, [r11+38h]
0x18001ced0  mov     rsi, [r11+40h]
0x18001ced4  mov     rsp, r11
0x18001ced7  pop     r15
0x18001ced9  pop     r14
0x18001cedb  pop     r12
0x18001cedd  pop     rdi
0x18001cede  pop     rbp
0x18001cedf  retn
```
