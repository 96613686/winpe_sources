# wil::reg::get_value_nothrow(HKEY__ *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180023160`
- end: `0x180023249`
- name: `?get_value_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBG1AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z`
- size: `233`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a154`
- `0x18001c784`
- `0x18001cce4`

## callees

- `0x180023160`
- `0x180023834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023194`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002318c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002318c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800231d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800231d7`

## pseudocode

```c
__int64 __fastcall wil::reg::get_value_nothrow(HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue, PVOID *a4)
{
  PVOID v4; // rsi
  DWORD LastError; // ebx
  DWORD i; // eax
  LSTATUS ValueW; // eax
  unsigned int v12; // ebx
  DWORD v13; // edx
  __int64 result; // rax
  DWORD pcbData; // [rsp+80h] [rbp+8h] BYREF

  v4 = *a4;
  if ( *a4 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v4);
    SetLastError(LastError);
  }
  *a4 = 0;
  for ( i = 0; ; i = pcbData )
  {
    pcbData = i;
    ValueW = RegGetValueW(hkey, lpSubKey, lpValue, 0x10000006u, 0, *a4, &pcbData);
    v12 = ValueW;
    if ( ValueW > 0 )
      v12 = (unsigned __int16)ValueW | 0x80070000;
    if ( v12 == -2147024662 )
    {
      v13 = pcbData;
      goto LABEL_12;
    }
    if ( (v12 & 0x80000000) != 0 )
      return v12;
    v13 = pcbData;
    if ( *a4 )
      break;
    if ( !pcbData )
      return v12;
LABEL_12:
    result = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a4, v13);
    if ( (int)result < 0 )
      return result;
  }
  if ( !pcbData )
    return v12;
  result = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a4, pcbData);
  if ( (int)result >= 0 )
    return v12;
  return result;
}

```

## disassembly

```asm
0x180023160  push    rbx
0x180023162  push    rbp
0x180023163  push    rsi
0x180023164  push    rdi
0x180023165  push    r14
0x180023167  push    r15
0x180023169  sub     rsp, 48h
0x18002316d  mov     rsi, [r9]
0x180023170  mov     rdi, r9
0x180023173  mov     rbp, r8
0x180023176  mov     r14, rdx
0x180023179  mov     r15, rcx
0x18002317c  test    rsi, rsi
0x18002317f  jz      short loc_18002319A
0x180023181  call    cs:__imp_GetLastError
0x180023187  mov     rcx, rsi; pv
0x18002318a  mov     ebx, eax
0x18002318c  call    cs:__imp_CoTaskMemFree
0x180023192  mov     ecx, ebx; dwErrCode
0x180023194  call    cs:__imp_SetLastError
0x18002319a  mov     qword ptr [rdi], 0
0x1800231a1  xor     eax, eax
0x1800231a3  mov     [rsp+78h+arg_0], eax
0x1800231aa  mov     r9d, 10000006h; dwFlags
0x1800231b0  lea     rax, [rsp+78h+arg_0]
0x1800231b8  mov     r8, rbp; lpValue
0x1800231bb  mov     [rsp+78h+pcbData], rax; pcbData
0x1800231c0  mov     rdx, r14; lpSubKey
0x1800231c3  mov     rax, [rdi]
0x1800231c6  mov     rcx, r15; hkey
0x1800231c9  mov     [rsp+78h+pvData], rax; pvData
0x1800231ce  mov     [rsp+78h+pdwType], 0; pdwType
0x1800231d7  call    cs:__imp_RegGetValueW
0x1800231dd  mov     ebx, eax
0x1800231df  test    eax, eax
0x1800231e1  jle     short loc_1800231EC
0x1800231e3  movzx   ebx, ax
0x1800231e6  or      ebx, 80070000h
0x1800231ec  cmp     ebx, 800700EAh
0x1800231f2  jz      short loc_18002320B
0x1800231f4  test    ebx, ebx
0x1800231f6  js      short loc_18002323A
0x1800231f8  cmp     qword ptr [rdi], 0
0x1800231fc  mov     edx, [rsp+78h+arg_0]
0x180023203  jnz     short loc_18002322A
0x180023205  test    edx, edx
0x180023207  jz      short loc_18002323A
0x180023209  jmp     short loc_180023212
0x18002320b  mov     edx, [rsp+78h+arg_0]
0x180023212  mov     rcx, rdi
0x180023215  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002321a  test    eax, eax
0x18002321c  js      short loc_18002323C
0x18002321e  mov     eax, [rsp+78h+arg_0]
0x180023225  jmp     loc_1800231A3
0x18002322a  test    edx, edx
0x18002322c  jz      short loc_18002323A
0x18002322e  mov     rcx, rdi
0x180023231  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@4@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x180023236  test    eax, eax
0x180023238  js      short loc_18002323C
0x18002323a  mov     eax, ebx
0x18002323c  add     rsp, 48h
0x180023240  pop     r15
0x180023242  pop     r14
0x180023244  pop     rdi
0x180023245  pop     rsi
0x180023246  pop     rbp
0x180023247  pop     rbx
0x180023248  retn
```
