# NetSetupSvcKernelServices::SendTdiCommand(Tdi::Command,wchar_t const *,wchar_t const *,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18000ee50`
- end: `0x18000efc8`
- name: `?SendTdiCommand@NetSetupSvcKernelServices@@UEAAXW4Command@Tdi@@PEB_W1AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `376`
- prototype: `void __fastcall(__int64, int, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800027c0`
- `0x18000d384`
- `0x18000d974`
- `0x18000ea48`
- `0x18000ec8c`
- `0x18000ecb8`
- `0x18000ed5c`
- `0x18000edc8`
- `0x18000ee50`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ef86`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ef86`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NetSetupSvcKernelServices::SendTdiCommand(__int64 a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v8; // edi
  int v9; // esi
  char *v10; // rcx
  char *v11; // rcx
  __int64 v12; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+48h] [rbp-38h] BYREF
  LPVOID lpInBuffer; // [rsp+50h] [rbp-30h] BYREF
  __int64 v15; // [rsp+58h] [rbp-28h]
  HANDLE hDevice; // [rsp+68h] [rbp-18h] BYREF

  std::vector<unsigned char>::vector<unsigned char>(&lpInBuffer, 28);
  NdisHandle::NdisHandle((NdisHandle *)&hDevice);
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v12 = 0;
      AppendStringToBuffer(&lpInBuffer, a4, &v12);
      v8 = (int)lpInBuffer;
      v9 = v15;
      std::vector<unsigned char>::_Insert_counted_range<unsigned char const *>(&lpInBuffer, v15, *a5, a5[1] - *a5);
      v10 = (char *)lpInBuffer;
      *(_DWORD *)lpInBuffer = 1;
      *(_QWORD *)(v10 + 12) = v12;
      *((_DWORD *)v10 + 6) = *((_DWORD *)a5 + 2) - *(_DWORD *)a5;
      *((_DWORD *)v10 + 5) = v9 - v8;
      goto LABEL_7;
    }
    if ( a2 != 2 )
    {
      __debugbreak();
      goto LABEL_7;
    }
  }
  v12 = 0;
  v13 = 0;
  AppendStringToBuffer(&lpInBuffer, a3, &v12);
  AppendStringToBuffer(&lpInBuffer, a4, &v13);
  v11 = (char *)lpInBuffer;
  *(_DWORD *)lpInBuffer = a2 != 0 ? 2 : 0;
  *(_QWORD *)(v11 + 4) = v12;
  *(_QWORD *)(v11 + 12) = v13;
LABEL_7:
  if ( !DeviceIoControl(hDevice, 0x170808u, lpInBuffer, v15 - (_DWORD)lpInBuffer, 0, 0, 0, 0) )
    Win32Exception::ThrowLastError();
  std::unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullOrNegativeOneIsInvalid>>::~unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullOrNegativeOneIsInvalid>>(&hDevice);
  std::vector<unsigned char>::_Tidy((__int64)&lpInBuffer);
}

```

## disassembly

```asm
0x18000ee50  mov     [rsp-18h+arg_0], rbx
0x18000ee55  push    rbp
0x18000ee56  push    rsi
0x18000ee57  push    rdi
0x18000ee58  mov     rbp, rsp
0x18000ee5b  sub     rsp, 80h
0x18000ee62  mov     rax, cs:__security_cookie
0x18000ee69  xor     rax, rsp
0x18000ee6c  mov     [rbp+var_10], rax
0x18000ee70  mov     rdi, r9
0x18000ee73  mov     rsi, r8
0x18000ee76  mov     ebx, edx
0x18000ee78  mov     edx, 1Ch
0x18000ee7d  lea     rcx, [rbp+lpInBuffer]
0x18000ee81  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000ee86  nop
0x18000ee87  lea     rcx, [rbp+hDevice]; this
0x18000ee8b  call    ??0NdisHandle@@QEAA@K@Z; NdisHandle::NdisHandle(ulong)
0x18000ee90  nop
0x18000ee91  mov     ecx, ebx
0x18000ee93  test    ebx, ebx
0x18000ee95  jz      short loc_18000EF02
0x18000ee97  sub     ecx, 1
0x18000ee9a  jz      short loc_18000EEA7
0x18000ee9c  cmp     ecx, 1
0x18000ee9f  jz      short loc_18000EF02
0x18000eea1  int     3; Trap to Debugger
0x18000eea2  jmp     loc_18000EF4F
0x18000eea7  mov     [rbp+var_40], 0
0x18000eeaf  lea     r8, [rbp+var_40]
0x18000eeb3  mov     rdx, rdi
0x18000eeb6  lea     rcx, [rbp+lpInBuffer]
0x18000eeba  call    ?AppendStringToBuffer@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAU_NDIS_OFFSET_AND_LENGTH@@@Z; AppendStringToBuffer(std::vector<uchar> &,wchar_t const *,_NDIS_OFFSET_AND_LENGTH *)
0x18000eebf  mov     rdi, [rbp+lpInBuffer]
0x18000eec3  mov     rsi, [rbp+var_28]
0x18000eec7  mov     rbx, [rbp+arg_20]
0x18000eecb  mov     r9, [rbx+8]
0x18000eecf  sub     r9, [rbx]
0x18000eed2  mov     r8, [rbx]
0x18000eed5  mov     rdx, rsi
0x18000eed8  lea     rcx, [rbp+lpInBuffer]
0x18000eedc  call    ??$_Insert_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,unsigned __int64)
0x18000eee1  mov     rcx, [rbp+lpInBuffer]
0x18000eee5  mov     dword ptr [rcx], 1
0x18000eeeb  mov     rax, [rbp+var_40]
0x18000eeef  mov     [rcx+0Ch], rax
0x18000eef3  mov     eax, [rbx+8]
0x18000eef6  sub     eax, [rbx]
0x18000eef8  mov     [rcx+18h], eax
0x18000eefb  sub     esi, edi
0x18000eefd  mov     [rcx+14h], esi
0x18000ef00  jmp     short loc_18000EF4F
0x18000ef02  mov     [rbp+var_40], 0
0x18000ef0a  mov     [rbp+var_38], 0
0x18000ef12  lea     r8, [rbp+var_40]
0x18000ef16  mov     rdx, rsi
0x18000ef19  lea     rcx, [rbp+lpInBuffer]
0x18000ef1d  call    ?AppendStringToBuffer@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAU_NDIS_OFFSET_AND_LENGTH@@@Z; AppendStringToBuffer(std::vector<uchar> &,wchar_t const *,_NDIS_OFFSET_AND_LENGTH *)
0x18000ef22  lea     r8, [rbp+var_38]
0x18000ef26  mov     rdx, rdi
0x18000ef29  lea     rcx, [rbp+lpInBuffer]
0x18000ef2d  call    ?AppendStringToBuffer@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAU_NDIS_OFFSET_AND_LENGTH@@@Z; AppendStringToBuffer(std::vector<uchar> &,wchar_t const *,_NDIS_OFFSET_AND_LENGTH *)
0x18000ef32  mov     rcx, [rbp+lpInBuffer]
0x18000ef36  neg     ebx
0x18000ef38  sbb     eax, eax
0x18000ef3a  and     eax, 2
0x18000ef3d  mov     [rcx], eax
0x18000ef3f  mov     rax, [rbp+var_40]
0x18000ef43  mov     [rcx+4], rax
0x18000ef47  mov     rax, [rbp+var_38]
0x18000ef4b  mov     [rcx+0Ch], rax
0x18000ef4f  mov     r8, [rbp+lpInBuffer]; lpInBuffer
0x18000ef53  mov     r9d, dword ptr [rbp+var_28]
0x18000ef57  sub     r9d, r8d; nInBufferSize
0x18000ef5a  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x18000ef63  mov     [rsp+80h+lpBytesReturned], 0; lpBytesReturned
0x18000ef6c  mov     [rsp+80h+nOutBufferSize], 0; nOutBufferSize
0x18000ef74  mov     [rsp+80h+lpOutBuffer], 0; lpOutBuffer
0x18000ef7d  mov     edx, 170808h; dwIoControlCode
0x18000ef82  mov     rcx, [rbp+hDevice]; hDevice
0x18000ef86  call    cs:__imp_DeviceIoControl
0x18000ef8c  test    eax, eax
0x18000ef8e  jnz     short loc_18000EF96
0x18000ef90  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x18000ef96  lea     rcx, [rbp+hDevice]
0x18000ef9a  call    ??1?$unique_ptr@XU?$SafeHandleCleanupWithCloseHandle@USafeHandleNullOrNegativeOneIsInvalid@@@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullOrNegativeOneIsInvalid>>::~unique_ptr<void,SafeHandleCleanupWithCloseHandle<SafeHandleNullOrNegativeOneIsInvalid>>(void)
0x18000ef9f  nop
0x18000efa0  lea     rcx, [rbp+lpInBuffer]
0x18000efa4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000efa9  mov     rcx, [rbp+var_10]
0x18000efad  xor     rcx, rsp; StackCookie
0x18000efb0  call    __security_check_cookie
0x18000efb5  mov     rbx, [rsp+80h+arg_0]
0x18000efbd  add     rsp, 80h
0x18000efc4  pop     rdi
0x18000efc5  pop     rsi
0x18000efc6  pop     rbp
0x18000efc7  retn
```
