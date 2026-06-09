# CBroker::SebBroker::FindEvent(Broker::ApplicationIdentity const &,_CSebiEventType)

- ea: `0x18001ad04`
- end: `0x18001ae0d`
- name: `?FindEvent@SebBroker@CBroker@@AEAA?AV?$shared_ptr@VSebEvent@CBroker@@@std@@AEBUApplicationIdentity@Broker@@W4_CSebiEventType@@@Z`
- size: `265`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, PSID *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006e00`

## callees

- `0x1800076a0`
- `0x18000b168`
- `0x180016ac4`
- `0x180017120`
- `0x1800171bc`
- `0x18001ad04`
- `0x18001ae14`

## pseudocode

```c
_QWORD *__fastcall CBroker::SebBroker::FindEvent(__int64 a1, _QWORD *a2, PSID *a3, int a4)
{
  PSID *v8; // r8
  _QWORD *v9; // rdx
  __int64 *First__lambda_cbeaae26278add60d0c1457e76ea093d; // rax
  _BYTE v12[8]; // [rsp+30h] [rbp-78h] BYREF
  std::_Ref_count_base *v13; // [rsp+38h] [rbp-70h]
  _QWORD v14[2]; // [rsp+40h] [rbp-68h] BYREF
  int v15; // [rsp+50h] [rbp-58h]
  int v16; // [rsp+54h] [rbp-54h]
  _QWORD v17[2]; // [rsp+60h] [rbp-48h] BYREF
  int v18; // [rsp+74h] [rbp-34h]

  std::vector<_GUID>::vector<_GUID>(v17);
  *v9 = 0;
  v9[1] = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), *v8);
  v16 = v18;
  v14[0] = a1;
  v14[1] = a3;
  v15 = a4;
  First__lambda_cbeaae26278add60d0c1457e76ea093d = (__int64 *)Broker::BrokerEventTable_CBroker::SebEvent_::FindFirst__lambda_cbeaae26278add60d0c1457e76ea093d___(
                                                                a1 + 16,
                                                                v12,
                                                                v14);
  std::shared_ptr<CBroker::SebBroker>::operator=(a2, First__lambda_cbeaae26278add60d0c1457e76ea093d);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), *a3);
  std::vector<_GUID>::_Tidy(v17);
  return a2;
}

```

## disassembly

```asm
0x18001ad04  push    rbx
0x18001ad06  push    rbp
0x18001ad07  push    rsi
0x18001ad08  push    rdi
0x18001ad09  sub     rsp, 88h
0x18001ad10  mov     rsi, rcx
0x18001ad13  mov     ebp, r9d
0x18001ad16  lea     rcx, [rsp+0A8h+var_48]
0x18001ad1b  mov     rbx, r8
0x18001ad1e  mov     rdi, rdx
0x18001ad21  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001ad26  mov     qword ptr [rdx], 0
0x18001ad2d  mov     qword ptr [rdx+8], 0
0x18001ad35  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad3c  test    byte ptr [rcx+1Ch], 1
0x18001ad40  jz      short loc_18001AD73
0x18001ad42  cmp     byte ptr [rcx+19h], 4
0x18001ad46  jb      short loc_18001AD73
0x18001ad48  mov     rax, [r8]
0x18001ad4b  lea     r9, [r8+38h]
0x18001ad4f  cmp     qword ptr [r9+18h], 7
0x18001ad54  jbe     short loc_18001AD59
0x18001ad56  mov     r9, [r9]
0x18001ad59  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ad5d  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001ad64  mov     edx, 23h ; '#'
0x18001ad69  mov     [rsp+0A8h+pSid], rax; pSid
0x18001ad6e  call    WPP_SF_S_sid_
0x18001ad73  mov     eax, [rsp+0A8h+var_34]
0x18001ad77  lea     rcx, [rsi+10h]
0x18001ad7b  lea     r8, [rsp+0A8h+var_68]
0x18001ad80  mov     [rsp+0A8h+var_54], eax
0x18001ad84  lea     rdx, [rsp+0A8h+var_78]
0x18001ad89  mov     [rsp+0A8h+var_68], rsi
0x18001ad8e  mov     [rsp+0A8h+var_60], rbx
0x18001ad93  mov     [rsp+0A8h+var_58], ebp
0x18001ad97  call    Broker__BrokerEventTable_CBroker__SebEvent___FindFirst__lambda_cbeaae26278add60d0c1457e76ea093d___
0x18001ad9c  mov     rdx, rax
0x18001ad9f  mov     rcx, rdi
0x18001ada2  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001ada7  mov     rcx, [rsp+0A8h+var_70]; this
0x18001adac  test    rcx, rcx
0x18001adaf  jz      short loc_18001ADB6
0x18001adb1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001adb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adbd  test    byte ptr [rcx+1Ch], 1
0x18001adc1  jz      short loc_18001ADF4
0x18001adc3  cmp     byte ptr [rcx+19h], 4
0x18001adc7  jb      short loc_18001ADF4
0x18001adc9  mov     rax, [rbx]
0x18001adcc  lea     r9, [rbx+38h]
0x18001add0  cmp     qword ptr [r9+18h], 7
0x18001add5  jbe     short loc_18001ADDA
0x18001add7  mov     r9, [r9]
0x18001adda  mov     rcx, [rcx+10h]; LoggerHandle
0x18001adde  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001ade5  mov     edx, 24h ; '$'
0x18001adea  mov     [rsp+0A8h+pSid], rax; pSid
0x18001adef  call    WPP_SF_S_sid_
0x18001adf4  lea     rcx, [rsp+0A8h+var_48]
0x18001adf9  call    ?_Tidy@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXXZ; std::vector<_GUID>::_Tidy(void)
0x18001adfe  mov     rax, rdi
0x18001ae01  add     rsp, 88h
0x18001ae08  pop     rdi
0x18001ae09  pop     rsi
0x18001ae0a  pop     rbp
0x18001ae0b  pop     rbx
0x18001ae0c  retn
```
