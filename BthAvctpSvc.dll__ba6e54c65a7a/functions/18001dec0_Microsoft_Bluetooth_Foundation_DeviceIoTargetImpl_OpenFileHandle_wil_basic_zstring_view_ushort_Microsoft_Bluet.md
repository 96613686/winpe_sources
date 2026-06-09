# Microsoft::Bluetooth::Foundation::DeviceIoTargetImpl::OpenFileHandle(wil::basic_zstring_view<ushort>,Microsoft::Bluetooth::Foundation::DeviceIoTarget::Options const &)

- ea: `0x18001dec0`
- end: `0x18001dfa0`
- name: `?OpenFileHandle@DeviceIoTargetImpl@Foundation@Bluetooth@Microsoft@@EEAAXV?$basic_zstring_view@G@wil@@AEBUOptions@DeviceIoTarget@234@@Z`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000dca8`
- `0x18000e0c0`
- `0x180012130`
- `0x18001dec0`
- `0x18004fbdc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001df40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001df40`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::DeviceIoTargetImpl::OpenFileHandle(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3)
{
  _QWORD *v3; // rdi
  int v6; // r9d
  DWORD v7; // r8d
  int v8; // ecx
  __int64 result; // rax
  HANDLE FileW; // rax
  const char *v11; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-38h]
  __int128 v13; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = (_QWORD *)(a1 + 264);
  if ( *(_BYTE *)(a3 + 8) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v3,
      -1);
    v6 = *(_DWORD *)(a3 + 4);
    v7 = *(_DWORD *)a3;
    v13 = *(_OWORD *)a2;
    result = Microsoft::Bluetooth::Foundation::DeviceIoTargetImpl::BrokeredCreateFile(v8, (unsigned int)&v13, v7, v6);
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10AE,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
        (const char *)(unsigned int)result,
        dwCreationDisposition);
  }
  else
  {
    FileW = CreateFileW(*a2, *(_DWORD *)a3, *(_DWORD *)(a3 + 4), 0, 3u, 0x40000080u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v3,
      FileW);
    result = *v3 + 1LL;
    if ( (result & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x10BB,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
        v11);
  }
  return result;
}

```

## disassembly

```asm
0x18001dec0  mov     [rsp+arg_0], rbx
0x18001dec5  mov     [rsp+arg_8], rsi
0x18001deca  push    rdi
0x18001decb  sub     rsp, 50h
0x18001decf  cmp     byte ptr [r8+8], 0
0x18001ded4  lea     rdi, [rcx+108h]
0x18001dedb  mov     rbx, r8
0x18001dede  mov     rsi, rdx
0x18001dee1  jz      short loc_18001DF1B
0x18001dee3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001dee7  mov     rcx, rdi
0x18001deea  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001deef  movups  xmm0, xmmword ptr [rsi]
0x18001def2  mov     eax, [rbx+0Ch]
0x18001def5  lea     rdx, [rsp+58h+var_18]
0x18001defa  mov     r9d, [rbx+4]
0x18001defe  mov     r8d, [rbx]
0x18001df01  mov     [rsp+58h+hTemplateFile], rdi
0x18001df06  movdqu  [rsp+58h+var_18], xmm0
0x18001df0c  mov     [rsp+58h+dwFlagsAndAttributes], eax
0x18001df10  call    ?BrokeredCreateFile@DeviceIoTargetImpl@Foundation@Bluetooth@Microsoft@@AEAAJV?$basic_zstring_view@G@wil@@KKKKPEAPEAX@Z; Microsoft::Bluetooth::Foundation::DeviceIoTargetImpl::BrokeredCreateFile(wil::basic_zstring_view<ushort>,ulong,ulong,ulong,ulong,void * *)
0x18001df15  test    eax, eax
0x18001df17  js      short loc_18001DF86
0x18001df19  jmp     short loc_18001DF5F
0x18001df1b  mov     r8d, [r8+4]; dwShareMode
0x18001df1f  xor     r9d, r9d; lpSecurityAttributes
0x18001df22  mov     edx, [rbx]; dwDesiredAccess
0x18001df24  mov     rcx, [rsi]; lpFileName
0x18001df27  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18001df30  mov     [rsp+58h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18001df38  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18001df40  call    cs:__imp_CreateFileW
0x18001df46  mov     rdx, rax
0x18001df49  mov     rcx, rdi
0x18001df4c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001df51  mov     rax, [rdi]
0x18001df54  inc     rax
0x18001df57  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001df5d  jz      short loc_18001DF6F
0x18001df5f  mov     rbx, [rsp+58h+arg_0]
0x18001df64  mov     rsi, [rsp+58h+arg_8]
0x18001df69  add     rsp, 50h
0x18001df6d  pop     rdi
0x18001df6e  retn
0x18001df6f  mov     rcx, [rsp+58h]; this
0x18001df74  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x18001df7b  mov     edx, 10BBh; void *
0x18001df80  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001df86  mov     rcx, [rsp+58h]; this
0x18001df8b  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x18001df92  mov     r9d, eax; char *
0x18001df95  mov     edx, 10AEh; void *
0x18001df9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
