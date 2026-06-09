# Broker::DeviceInterfaceArrivalEvent::IsInterfaceTriggerSatisfiedWithRetry(void)

- ea: `0x180018a38`
- end: `0x180018ba2`
- name: `?IsInterfaceTriggerSatisfiedWithRetry@DeviceInterfaceArrivalEvent@Broker@@AEAAKXZ`
- size: `362`
- prototype: `__int64 __fastcall(Broker::DeviceInterfaceArrivalEvent *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021af0`

## callees

- `0x18000b168`
- `0x180018a38`
- `0x180019130`
- `0x180019170`
- `0x180019224`
- `0x18001d9a0`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180018a6f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180018a6f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180018afe`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180018afe`

## pseudocode

```c
__int64 __fastcall Broker::DeviceInterfaceArrivalEvent::IsInterfaceTriggerSatisfiedWithRetry(
        Broker::DeviceInterfaceArrivalEvent *this)
{
  CONFIGRET Device_Interface_List_SizeW; // eax
  ULONG v3; // r9d
  char *v4; // rsi
  unsigned __int64 v5; // rcx
  WCHAR *v6; // rax
  size_t v7; // rbx
  __int64 v8; // rcx
  unsigned int matched; // ebx
  PZZWSTR Buffer; // [rsp+30h] [rbp-40h] BYREF
  void *v12; // [rsp+38h] [rbp-38h]
  __int64 v13; // [rsp+40h] [rbp-30h]
  void **pExceptionObject; // [rsp+48h] [rbp-28h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h]
  int v16; // [rsp+60h] [rbp-10h]
  CONFIGRET v17; // [rsp+68h] [rbp-8h]
  ULONG pulLen; // [rsp+90h] [rbp+20h] BYREF

  pulLen = 0;
  std::vector<_GUID>::vector<_GUID>(&Buffer);
  do
  {
    Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, (LPGUID)((char *)this + 40), 0, 0);
    if ( Device_Interface_List_SizeW )
      goto LABEL_19;
    v3 = pulLen;
    if ( pulLen == 1 )
    {
      if ( Buffer )
        std::_Deallocate<16>(Buffer, 2 * ((v13 - (__int64)Buffer) >> 1));
      return 0;
    }
    v4 = (char *)v12;
    v5 = ((_BYTE *)v12 - (_BYTE *)Buffer) >> 1;
    if ( pulLen >= v5 )
    {
      if ( pulLen <= v5 )
        goto LABEL_11;
      if ( pulLen > (unsigned __int64)((v13 - (__int64)Buffer) >> 1) )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&Buffer, pulLen);
        v3 = pulLen;
        goto LABEL_11;
      }
      v7 = 2 * (pulLen - v5);
      memset_0(v12, 0, v7);
      v6 = (WCHAR *)&v4[v7];
      v3 = pulLen;
    }
    else
    {
      v6 = &Buffer[pulLen];
    }
    v12 = v6;
LABEL_11:
    Device_Interface_List_SizeW = CM_Get_Device_Interface_ListW((LPGUID)((char *)this + 40), 0, Buffer, v3, 0);
  }
  while ( Device_Interface_List_SizeW == 26 );
  if ( Device_Interface_List_SizeW )
  {
LABEL_19:
    v15 = 0;
    v16 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v17 = Device_Interface_List_SizeW;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  matched = (unsigned __int8)Broker::DeviceInterfaceArrivalEvent::MatchString__lambda_860c55bb1ab34bdf4cceaf81fa775de5___(
                               v8,
                               Buffer,
                               pulLen,
                               this);
  if ( Buffer )
    std::_Deallocate<16>(Buffer, 2 * ((v13 - (__int64)Buffer) >> 1));
  return matched;
}

```

## disassembly

```asm
0x180018a38  mov     [rsp-18h+arg_8], rbx
0x180018a3d  mov     [rsp-18h+arg_10], rsi
0x180018a42  push    rbp
0x180018a43  push    rdi
0x180018a44  push    r14
0x180018a46  mov     rbp, rsp
0x180018a49  sub     rsp, 70h
0x180018a4d  mov     rdi, rcx
0x180018a50  mov     [rbp+pulLen], 0
0x180018a57  lea     rcx, [rbp+Buffer]
0x180018a5b  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180018a60  nop
0x180018a61  xor     r9d, r9d; ulFlags
0x180018a64  xor     r8d, r8d; pDeviceID
0x180018a67  lea     rdx, [rdi+28h]; InterfaceClassGuid
0x180018a6b  lea     rcx, [rbp+pulLen]; pulLen
0x180018a6f  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x180018a75  test    eax, eax
0x180018a77  jnz     loc_180018B75
0x180018a7d  mov     r9d, [rbp+pulLen]
0x180018a81  cmp     r9d, 1
0x180018a85  jz      loc_180018B56
0x180018a8b  mov     ebx, r9d
0x180018a8e  mov     rdx, [rbp+Buffer]
0x180018a92  mov     rsi, [rbp+var_38]
0x180018a96  mov     rcx, rsi
0x180018a99  sub     rcx, rdx
0x180018a9c  sar     rcx, 1
0x180018a9f  cmp     r9, rcx
0x180018aa2  jnb     short loc_180018AAA
0x180018aa4  lea     rax, [rdx+r9*2]
0x180018aa8  jmp     short loc_180018AE8
0x180018aaa  jbe     short loc_180018AEC
0x180018aac  mov     rax, [rbp+var_30]
0x180018ab0  sub     rax, rdx
0x180018ab3  sar     rax, 1
0x180018ab6  cmp     rbx, rax
0x180018ab9  jbe     short loc_180018ACD
0x180018abb  mov     rdx, rbx
0x180018abe  lea     rcx, [rbp+Buffer]
0x180018ac2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180018ac7  mov     r9d, [rbp+pulLen]
0x180018acb  jmp     short loc_180018AEC
0x180018acd  sub     rbx, rcx
0x180018ad0  add     rbx, rbx
0x180018ad3  mov     r8, rbx; Size
0x180018ad6  xor     edx, edx; Val
0x180018ad8  mov     rcx, rsi; void *
0x180018adb  call    memset_0
0x180018ae0  lea     rax, [rbx+rsi]
0x180018ae4  mov     r9d, [rbp+pulLen]; BufferLen
0x180018ae8  mov     [rbp+var_38], rax
0x180018aec  mov     [rsp+70h+ulFlags], 0; ulFlags
0x180018af4  mov     r8, [rbp+Buffer]; Buffer
0x180018af8  xor     edx, edx; pDeviceID
0x180018afa  lea     rcx, [rdi+28h]; InterfaceClassGuid
0x180018afe  call    cs:__imp_CM_Get_Device_Interface_ListW
0x180018b04  cmp     eax, 1Ah
0x180018b07  jz      loc_180018A61
0x180018b0d  test    eax, eax
0x180018b0f  jnz     short loc_180018B75
0x180018b11  mov     r9, rdi
0x180018b14  mov     r8d, [rbp+pulLen]
0x180018b18  mov     rdx, [rbp+Buffer]
0x180018b1c  call    Broker__DeviceInterfaceArrivalEvent__MatchString__lambda_860c55bb1ab34bdf4cceaf81fa775de5___
0x180018b21  movzx   ebx, al
0x180018b24  mov     rcx, [rbp+Buffer]
0x180018b28  test    rcx, rcx
0x180018b2b  jz      short loc_180018B3F
0x180018b2d  mov     rdx, [rbp+var_30]
0x180018b31  sub     rdx, rcx
0x180018b34  sar     rdx, 1
0x180018b37  add     rdx, rdx
0x180018b3a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018b3f  mov     eax, ebx
0x180018b41  lea     r11, [rsp+70h+var_s0]
0x180018b46  mov     rbx, [r11+28h]
0x180018b4a  mov     rsi, [r11+30h]
0x180018b4e  mov     rsp, r11
0x180018b51  pop     r14
0x180018b53  pop     rdi
0x180018b54  pop     rbp
0x180018b55  retn
0x180018b56  mov     rcx, [rbp+Buffer]
0x180018b5a  test    rcx, rcx
0x180018b5d  jz      short loc_180018B71
0x180018b5f  mov     rdx, [rbp+var_30]
0x180018b63  sub     rdx, rcx
0x180018b66  sar     rdx, 1
0x180018b69  add     rdx, rdx
0x180018b6c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018b71  xor     eax, eax
0x180018b73  jmp     short loc_180018B41
0x180018b75  xorps   xmm0, xmm0
0x180018b78  movups  [rbp+var_20], xmm0
0x180018b7c  mov     [rbp+var_10], 1
0x180018b83  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180018b8a  mov     [rbp+pExceptionObject], rcx
0x180018b8e  mov     [rbp+var_8], eax
0x180018b91  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180018b98  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018b9c  call    _CxxThrowException_0
```
