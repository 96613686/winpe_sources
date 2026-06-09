# CDPComDeviceQuery::CreateDeviceQueryInternal(CDPComNotifierData *)

- ea: `0x18001da9c`
- end: `0x18001dbc6`
- name: `?CreateDeviceQueryInternal@CDPComDeviceQuery@@AEAAJPEAUCDPComNotifierData@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *__hidden this, struct CDPComNotifierData *)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a750`
- `0x180036920`
- `0x180036a10`
- `0x1800384f0`
- `0x1800385c0`

## callees

- `0x180003e60`
- `0x180018970`
- `0x18001da9c`
- `0x18001dbcc`
- `0x18001ddf8`

## import_xrefs

- `cdp!CDPCreateDeviceQueryInternal` at `0x18001db1e`
- `cdp!CDPCreateDeviceQueryInternal` at `0x18001db1e`

## string_xrefs

- `0x18001dacd`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDPComDeviceQuery::CreateDeviceQueryInternal(CDPComDeviceQuery *this, struct CDPComNotifierData *a2)
{
  CDPComDeviceQuery *v2; // rbx
  std::_Ref_count_base *v4; // rax
  __int64 v5; // rdx
  int v6; // edi
  __int64 *v7; // rax
  __int64 v8; // rcx
  std::_Ref_count_base *v9; // rcx
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-8h]
  struct CDPComNotifierData *v12; // [rsp+58h] [rbp+18h] BYREF
  CDPComDeviceQuery *v13; // [rsp+60h] [rbp+20h] BYREF

  v12 = a2;
  v2 = this;
  if ( !a2 )
  {
    LODWORD(v12) = -2147024809;
    LODWORD(v13) = 427;
LABEL_3:
    Log<long &,char const (&)[28],int>(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)&v12,
      (unsigned int)".\\cdpcomdevicequery.cpp",
      (__int64)&v13);
    return (unsigned int)v12;
  }
  v4 = (CDPComDeviceQuery *)((char *)this + 104);
  if ( *((_QWORD *)this + 13) )
  {
    LODWORD(v12) = -2147221245;
    LODWORD(v13) = 430;
    goto LABEL_3;
  }
  v5 = *((_QWORD *)this + 15);
  LOBYTE(this) = *((_BYTE *)this + 160);
  v10 = 0;
  v11 = v4;
  v6 = CDPCreateDeviceQueryInternal(this, v5, &v10);
  cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(&v10);
  if ( v6 < 0 )
  {
    LODWORD(v12) = v6;
    LODWORD(v13) = 431;
    goto LABEL_3;
  }
  v13 = v2;
  v7 = (__int64 *)cdp::MakeSharedNoThrow<CDPComDeviceQuery::DeviceQueryCallback,CDPComNotifierData * &,CDPComDeviceQuery *>(
                    &v10,
                    &v12,
                    &v13);
  v8 = *v7;
  a2 = (struct CDPComNotifierData *)v7[1];
  *v7 = 0;
  v7[1] = 0;
  *((_QWORD *)v2 + 17) = v8;
  v9 = (std::_Ref_count_base *)*((_QWORD *)v2 + 18);
  *((_QWORD *)v2 + 18) = a2;
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  LODWORD(this) = (_DWORD)v11;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  if ( !*((_QWORD *)v2 + 17) )
  {
    LODWORD(v12) = -2147024882;
    LODWORD(v13) = 434;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001da9c  mov     [rsp-8+arg_0], rbx
0x18001daa1  mov     [rsp-8+arg_18], rdi
0x18001daa6  mov     [rsp-8+arg_8], rdx
0x18001daab  push    rbp
0x18001daac  mov     rbp, rsp
0x18001daaf  sub     rsp, 40h
0x18001dab3  mov     rbx, rcx
0x18001dab6  test    rdx, rdx
0x18001dab9  jnz     short loc_18001DAEA
0x18001dabb  mov     dword ptr [rbp+arg_8], 80070057h
0x18001dac2  mov     dword ptr [rbp+arg_10], 1ABh
0x18001dac9  lea     rax, [rbp+arg_10]
0x18001dacd  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18001dad4  mov     [rsp+40h+var_20], rax
0x18001dad9  lea     r8, [rbp+arg_8]
0x18001dadd  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001dae2  mov     eax, dword ptr [rbp+arg_8]
0x18001dae5  jmp     loc_18001DBB6
0x18001daea  lea     rax, [rcx+68h]
0x18001daee  cmp     qword ptr [rax], 0
0x18001daf2  jz      short loc_18001DB04
0x18001daf4  mov     dword ptr [rbp+arg_8], 80040103h
0x18001dafb  mov     dword ptr [rbp+arg_10], 1AEh
0x18001db02  jmp     short loc_18001DAC9
0x18001db04  mov     rdx, [rcx+78h]
0x18001db08  lea     r8, [rbp+var_10]
0x18001db0c  mov     cl, [rcx+0A0h]
0x18001db12  mov     [rbp+var_10], 0
0x18001db1a  mov     [rbp+var_8], rax
0x18001db1e  call    cs:__imp_CDPCreateDeviceQueryInternal
0x18001db24  lea     rcx, [rbp+var_10]
0x18001db28  mov     edi, eax
0x18001db2a  call    ??1?$address_of@VICDPDeviceQuery@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(void)
0x18001db2f  test    edi, edi
0x18001db31  jns     short loc_18001DB3F
0x18001db33  mov     dword ptr [rbp+arg_8], edi
0x18001db36  mov     dword ptr [rbp+arg_10], 1AFh
0x18001db3d  jmp     short loc_18001DAC9
0x18001db3f  lea     r8, [rbp+arg_10]
0x18001db43  mov     [rbp+arg_10], rbx
0x18001db47  lea     rdx, [rbp+arg_8]
0x18001db4b  lea     rcx, [rbp+var_10]
0x18001db4f  call    ??$MakeSharedNoThrow@VDeviceQueryCallback@CDPComDeviceQuery@@AEAPEAUCDPComNotifierData@@PEAV2@@cdp@@YA?AV?$shared_ptr@VDeviceQueryCallback@CDPComDeviceQuery@@@std@@AEAPEAUCDPComNotifierData@@$$QEAPEAVCDPComDeviceQuery@@@Z; cdp::MakeSharedNoThrow<CDPComDeviceQuery::DeviceQueryCallback,CDPComNotifierData * &,CDPComDeviceQuery *>(CDPComNotifierData * &,CDPComDeviceQuery * &&)
0x18001db54  mov     rcx, [rax]
0x18001db57  mov     rdx, [rax+8]
0x18001db5b  mov     qword ptr [rax], 0
0x18001db62  mov     qword ptr [rax+8], 0
0x18001db6a  mov     [rbx+88h], rcx
0x18001db71  mov     rcx, [rbx+90h]; this
0x18001db78  mov     [rbx+90h], rdx
0x18001db7f  test    rcx, rcx
0x18001db82  jz      short loc_18001DB89
0x18001db84  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001db89  mov     rcx, [rbp+var_8]; this
0x18001db8d  test    rcx, rcx
0x18001db90  jz      short loc_18001DB97
0x18001db92  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001db97  cmp     qword ptr [rbx+88h], 0
0x18001db9f  jnz     short loc_18001DBB4
0x18001dba1  mov     dword ptr [rbp+arg_8], 8007000Eh
0x18001dba8  mov     dword ptr [rbp+arg_10], 1B2h
0x18001dbaf  jmp     loc_18001DAC9
0x18001dbb4  xor     eax, eax
0x18001dbb6  mov     rbx, [rsp+40h+arg_0]
0x18001dbbb  mov     rdi, [rsp+40h+arg_18]
0x18001dbc0  add     rsp, 40h
0x18001dbc4  pop     rbp
0x18001dbc5  retn
```
