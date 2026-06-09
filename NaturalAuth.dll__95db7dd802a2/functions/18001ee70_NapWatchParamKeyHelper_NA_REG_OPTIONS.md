# NapWatchParamKeyHelper(NA_REG_OPTIONS *)

- ea: `0x18001ee70`
- end: `0x18001ef73`
- name: `?NapWatchParamKeyHelper@@YAKPEAUNA_REG_OPTIONS@@@Z`
- size: `259`
- prototype: `LSTATUS __fastcall(char *pvContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ee00`

## callees

- `0x18000a7f8`
- `0x18001ee70`

## import_xrefs

- `ntdll!RtlRegisterWait` at `0x18001ef31`
- `ntdll!RtlRegisterWait` at `0x18001ef31`
- `ntdll!RtlDeregisterWait` at `0x18001eefe`
- `ntdll!RtlDeregisterWait` at `0x18001eefe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001eeca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001eeca`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001eeee`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001eeee`

## pseudocode

```c
LSTATUS __fastcall NapWatchParamKeyHelper(char *pvContext)
{
  HKEY *v1; // rdi
  LSTATUS result; // eax
  LSTATUS v4; // edi
  NTSTATUS v5; // eax
  unsigned int v6; // eax
  DWORD v7; // [rsp+60h] [rbp+8h] BYREF

  v1 = (HKEY *)(pvContext + 16);
  v7 = 0;
  if ( *((_QWORD *)pvContext + 2)
    || (result = RegCreateKeyExW(
                   HKEY_LOCAL_MACHINE,
                   *((LPCWSTR *)pvContext + 3),
                   0,
                   (LPWSTR)&Class,
                   0,
                   0x20019u,
                   0,
                   v1,
                   &v7)) == 0 )
  {
    v4 = RegNotifyChangeKeyValue(*v1, 1, 0x10000005u, *((HANDLE *)pvContext + 1), 1);
    if ( !*(_QWORD *)pvContext || (v5 = RtlDeregisterWait(*(HANDLE *)pvContext), *(_QWORD *)pvContext = 0, v5 >= 0) )
    {
      if ( !v4 )
      {
        v6 = RtlRegisterWait(
               (PHANDLE)pvContext,
               *((HANDLE *)pvContext + 1),
               *((WAITORTIMERCALLBACKFUNC *)pvContext + 4),
               pvContext,
               0xFFFFFFFF,
               0x48u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, v6);
      }
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001ee70  mov     r11, rsp
0x18001ee73  mov     [r11+10h], rbx
0x18001ee77  push    rdi
0x18001ee78  sub     rsp, 50h
0x18001ee7c  lea     rdi, [rcx+10h]
0x18001ee80  mov     [rsp+58h+arg_0], 0
0x18001ee88  cmp     qword ptr [rdi], 0
0x18001ee8c  mov     rbx, rcx
0x18001ee8f  jnz     short loc_18001EED8
0x18001ee91  mov     rdx, [rcx+18h]; lpSubKey
0x18001ee95  lea     rax, [r11+8]
0x18001ee99  mov     [r11-18h], rax
0x18001ee9d  lea     r9, Class; lpClass
0x18001eea4  mov     [r11-20h], rdi
0x18001eea8  xor     r8d, r8d; Reserved
0x18001eeab  mov     qword ptr [r11-28h], 0
0x18001eeb3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eeba  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18001eec2  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001eeca  call    cs:__imp_RegCreateKeyExW
0x18001eed0  test    eax, eax
0x18001eed2  jnz     loc_18001EF68
0x18001eed8  mov     r9, [rbx+8]; hEvent
0x18001eedc  mov     edx, 1; bWatchSubtree
0x18001eee1  mov     rcx, [rdi]; hKey
0x18001eee4  mov     r8d, 10000005h; dwNotifyFilter
0x18001eeea  mov     [rsp+58h+dwOptions], edx; fAsynchronous
0x18001eeee  call    cs:__imp_RegNotifyChangeKeyValue
0x18001eef4  mov     rcx, [rbx]; hWaitHandle
0x18001eef7  mov     edi, eax
0x18001eef9  test    rcx, rcx
0x18001eefc  jz      short loc_18001EF0F
0x18001eefe  call    cs:__imp_RtlDeregisterWait
0x18001ef04  mov     qword ptr [rbx], 0
0x18001ef0b  test    eax, eax
0x18001ef0d  js      short loc_18001EF66
0x18001ef0f  test    edi, edi
0x18001ef11  jnz     short loc_18001EF66
0x18001ef13  mov     r8, [rbx+20h]; Callback
0x18001ef17  mov     r9, rbx; pvContext
0x18001ef1a  mov     rdx, [rbx+8]; hObject
0x18001ef1e  mov     rcx, rbx; phNewWaitObject
0x18001ef21  mov     [rsp+58h+samDesired], 48h ; 'H'; ulFlags
0x18001ef29  mov     [rsp+58h+dwOptions], 0FFFFFFFFh; ulMilliseconds
0x18001ef31  call    cs:__imp_RtlRegisterWait
0x18001ef37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef3e  lea     rdx, WPP_GLOBAL_Control
0x18001ef45  cmp     rcx, rdx
0x18001ef48  jz      short loc_18001EF66
0x18001ef4a  test    byte ptr [rcx+1Ch], 4
0x18001ef4e  jz      short loc_18001EF66
0x18001ef50  mov     rcx, [rcx+10h]
0x18001ef54  lea     edx, [rdi+29h]
0x18001ef57  mov     r9d, eax
0x18001ef5a  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001ef61  call    WPP_SF_d
0x18001ef66  mov     eax, edi
0x18001ef68  mov     rbx, [rsp+58h+arg_8]
0x18001ef6d  add     rsp, 50h
0x18001ef71  pop     rdi
0x18001ef72  retn
```
