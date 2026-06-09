# BluetoothSignal::Impl::PopulateDynamicLockResource(NA_SIGNAL_TYPE_INFO_BLUETOOTH_STATUS_AND_DEVICE_INFO *,ulong,ushort const *)

- ea: `0x180036dc8`
- end: `0x180036ee2`
- name: `?PopulateDynamicLockResource@Impl@BluetoothSignal@@SAXPEAUNA_SIGNAL_TYPE_INFO_BLUETOOTH_STATUS_AND_DEVICE_INFO@@KPEBG@Z`
- size: `282`
- prototype: `void __fastcall(struct NA_SIGNAL_TYPE_INFO_BLUETOOTH_STATUS_AND_DEVICE_INFO *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036c2c`

## callees

- `0x1800364e0`
- `0x180036dc8`
- `0x180037e94`
- `0x1800384ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180036df1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180036ebe`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180036df1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180036ebe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036e2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036e2e`

## string_xrefs

- `0x180036e1f`: `NaturalAuth.dll`

## pseudocode

```c
void __fastcall BluetoothSignal::Impl::PopulateDynamicLockResource(
        struct NA_SIGNAL_TYPE_INFO_BLUETOOTH_STATUS_AND_DEVICE_INFO *a1,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  int v5; // ebx
  BOOL v6; // ebp
  HMODULE ModuleHandleW; // rax
  int v8; // r8d
  char *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+40h] [rbp-38h]

  if ( a2 == 1 )
  {
    _o_wcsncpy_s((char *)a1 + 8, 262, a3, -1);
  }
  else
  {
    v11 = 0;
    v12 = 0;
    v5 = a2 - 1;
    v13 = 0;
    v6 = a2 > 2;
    if ( a2 <= 2 )
      v5 = 1;
    ModuleHandleW = GetModuleHandleW(L"NaturalAuth.dll");
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
                &v11,
                ModuleHandleW,
                (unsigned int)(v6 + 400),
                a3,
                v5) >= 0 )
    {
      v9 = (char *)a1 + 8;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v8, v6 + 400, (__int64)a3);
      v9 = (char *)a1 + 8;
      *((_WORD *)a1 + 4) = 0;
    }
    v10 = v11;
    v11 = 0;
    v13 = 0;
    v12 = 0;
    _o_wcsncpy_s(v9, 262, v10, -1);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v11);
  }
  *((_WORD *)a1 + 265) = 0;
}

```

## disassembly

```asm
0x180036dc8  push    rbx
0x180036dca  push    rbp
0x180036dcb  push    rsi
0x180036dcc  push    rdi
0x180036dcd  push    r15
0x180036dcf  sub     rsp, 50h
0x180036dd3  mov     r15d, 1
0x180036dd9  mov     rsi, r8
0x180036ddc  mov     rdi, rcx
0x180036ddf  cmp     edx, r15d
0x180036de2  jnz     short loc_180036DFC
0x180036de4  add     rcx, 8
0x180036de8  or      r9, 0FFFFFFFFFFFFFFFFh
0x180036dec  mov     edx, 106h
0x180036df1  call    cs:__imp__o_wcsncpy_s
0x180036df7  jmp     loc_180036ECE
0x180036dfc  xor     ebp, ebp
0x180036dfe  mov     [rsp+78h+var_48], 0
0x180036e07  cmp     edx, 2
0x180036e0a  mov     [rsp+78h+var_40], 0
0x180036e13  lea     ebx, [rdx-1]
0x180036e16  mov     [rsp+78h+var_38], 0
0x180036e1f  lea     rcx, aNaturalauthDll_0; "NaturalAuth.dll"
0x180036e26  setnbe  bpl
0x180036e2a  cmovbe  ebx, r15d
0x180036e2e  call    cs:__imp_GetModuleHandleW
0x180036e34  mov     r9, rsi
0x180036e37  mov     dword ptr [rsp+78h+var_58], ebx
0x180036e3b  mov     rdx, rax
0x180036e3e  lea     r8d, [rbp+190h]
0x180036e45  lea     rcx, [rsp+78h+var_48]
0x180036e4a  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180036e4f  test    eax, eax
0x180036e51  jns     short loc_180036E91
0x180036e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e5a  lea     rax, WPP_GLOBAL_Control
0x180036e61  cmp     rcx, rax
0x180036e64  jz      short loc_180036E86
0x180036e66  test    [rcx+1Ch], r15b
0x180036e6a  jz      short loc_180036E86
0x180036e6c  mov     rcx, [rcx+10h]
0x180036e70  lea     r9d, [rbp+190h]
0x180036e77  mov     edx, 2Ch ; ','
0x180036e7c  mov     [rsp+78h+var_58], rsi
0x180036e81  call    WPP_SF_dS
0x180036e86  lea     rcx, [rdi+8]
0x180036e8a  xor     eax, eax
0x180036e8c  mov     [rcx], ax
0x180036e8f  jmp     short loc_180036E95
0x180036e91  lea     rcx, [rdi+8]
0x180036e95  mov     r8, [rsp+78h+var_48]
0x180036e9a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180036e9e  mov     edx, 106h
0x180036ea3  mov     [rsp+78h+var_48], 0
0x180036eac  mov     [rsp+78h+var_38], 0
0x180036eb5  mov     [rsp+78h+var_40], 0
0x180036ebe  call    cs:__imp__o_wcsncpy_s
0x180036ec4  lea     rcx, [rsp+78h+var_48]
0x180036ec9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180036ece  xor     eax, eax
0x180036ed0  mov     [rdi+212h], ax
0x180036ed7  add     rsp, 50h
0x180036edb  pop     r15
0x180036edd  pop     rdi
0x180036ede  pop     rsi
0x180036edf  pop     rbp
0x180036ee0  pop     rbx
0x180036ee1  retn
```
