# IsDriverAnOSComponent

- ea: `0x180013af4`
- end: `0x180013bb6`
- name: `IsDriverAnOSComponent`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012cc8`
- `0x180012e50`

## callees

- `0x1800027c0`
- `0x180008d94`
- `0x18000d974`
- `0x180013af4`
- `0x18002a400`
- `0x18002bdfc`
- `0x18002c728`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall IsDriverAnOSComponent(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // r8
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  bool Boolean; // bl
  struct Property v12; // rax
  _BYTE v13[24]; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v14[24]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v15; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v16[8]; // [rsp+68h] [rbp-40h] BYREF
  _QWORD v17[4]; // [rsp+70h] [rbp-38h] BYREF
  char v18; // [rsp+90h] [rbp-18h]

  v4 = a2;
  v5 = a2 - 2;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 != 6 )
              return 0;
          }
        }
      }
    }
  }
  v15 = a1;
  NetSetup2::details::TryGetObjectWithFilter<NetSetup2::ActiveObject>(v16, &v15, v4, a3);
  if ( !v18 )
    return 0;
  v12.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                 (NetSetup2::ActiveObject *)v16,
                 (const struct _NETSETUPPROPKEY *)v13,
                 (unsigned int)NETSETUPPKEY_Driver_IsOSComponent).lpVtbl;
  Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)v12.lpVtbl);
  std::vector<unsigned char>::_Tidy((__int64)v14);
  if ( v18 )
    std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v17);
  return Boolean;
}

```

## disassembly

```asm
0x180013af4  push    rbx
0x180013af6  sub     rsp, 0A0h
0x180013afd  mov     rax, cs:__security_cookie
0x180013b04  xor     rax, rsp
0x180013b07  mov     [rsp+0A8h+var_10], rax
0x180013b0f  mov     r9, r8
0x180013b12  mov     r8d, edx
0x180013b15  sub     edx, 2
0x180013b18  jz      short loc_180013B37
0x180013b1a  sub     edx, 1
0x180013b1d  jz      short loc_180013B37
0x180013b1f  sub     edx, 1
0x180013b22  jz      short loc_180013B37
0x180013b24  sub     edx, 1
0x180013b27  jz      short loc_180013B37
0x180013b29  sub     edx, 1
0x180013b2c  jz      short loc_180013B37
0x180013b2e  cmp     edx, 6
0x180013b31  jz      short loc_180013B37
0x180013b33  xor     al, al
0x180013b35  jmp     short loc_180013B9D
0x180013b37  mov     [rsp+0A8h+var_48], rcx
0x180013b3c  lea     rdx, [rsp+0A8h+var_48]
0x180013b41  lea     rcx, [rsp+0A8h+var_40]
0x180013b46  call    ??$TryGetObjectWithFilter@VActiveObject@NetSetup2@@@details@NetSetup2@@YA?AV?$Optional@VActiveObject@NetSetup2@@@01@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::TryGetObjectWithFilter<NetSetup2::ActiveObject>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x180013b4b  nop
0x180013b4c  cmp     [rsp+0A8h+var_18], 0
0x180013b54  jnz     short loc_180013B5A
0x180013b56  xor     bl, bl
0x180013b58  jmp     short loc_180013B9B
0x180013b5a  lea     r8, NETSETUPPKEY_Driver_IsOSComponent
0x180013b61  lea     rdx, [rsp+0A8h+var_78]; struct _NETSETUPPROPKEY *
0x180013b66  lea     rcx, [rsp+0A8h+var_40]; this
0x180013b6b  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x180013b70  nop
0x180013b71  mov     rcx, rax; this
0x180013b74  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x180013b79  mov     bl, al
0x180013b7b  lea     rcx, [rsp+0A8h+var_60]
0x180013b80  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180013b85  nop
0x180013b86  cmp     [rsp+0A8h+var_18], 0
0x180013b8e  jz      short loc_180013B9B
0x180013b90  lea     rcx, [rsp+0A8h+var_38]
0x180013b95  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x180013b9a  nop
0x180013b9b  mov     al, bl
0x180013b9d  mov     rcx, [rsp+0A8h+var_10]
0x180013ba5  xor     rcx, rsp; StackCookie
0x180013ba8  call    __security_check_cookie
0x180013bad  add     rsp, 0A0h
0x180013bb4  pop     rbx
0x180013bb5  retn
```
