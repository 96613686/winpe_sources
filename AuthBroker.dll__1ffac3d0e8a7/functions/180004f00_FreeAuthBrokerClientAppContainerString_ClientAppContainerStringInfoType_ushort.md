# FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)

- ea: `0x180004f00`
- end: `0x180004f5b`
- name: `?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z`
- size: `91`
- prototype: `void __fastcall(ClientAppContainerStringInfoType infoType, wchar_t *string)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800045c0`
- `0x1800073bc`
- `0x180011034`
- `0x1800113a8`
- `0x1800154bc`
- `0x180019484`
- `0x18001e210`

## callees

- `0x180004f00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f39`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerFreeMemory` at `0x180004f44`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerFreeMemory` at `0x180004f44`

## pseudocode

```c
void __fastcall FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType infoType, wchar_t *string)
{
  int v3; // ecx
  int v4; // ecx
  HANDLE ProcessHeap; // rax

  if ( string )
  {
    if ( infoType )
    {
      v3 = infoType - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          if ( v4 == 1 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, string);
          }
        }
        else
        {
          CoTaskMemFree(string);
        }
      }
      else
      {
        AppContainerFreeMemory(string);
      }
    }
    else
    {
      LocalFree(string);
    }
  }
}

```

## disassembly

```asm
0x180004f00  test    string, string
0x180004f03  jz      short locret_180004F5A
0x180004f05  push    rbx
0x180004f06  sub     rsp, 20h
0x180004f0a  mov     rbx, string
0x180004f0d  test    infoType, infoType
0x180004f0f  jz      short loc_180004F4C
0x180004f11  sub     infoType, 1
0x180004f14  jz      short loc_180004F41
0x180004f16  sub     infoType, 1
0x180004f19  jz      short loc_180004F36
0x180004f1b  cmp     infoType, 1
0x180004f1e  jnz     short loc_180004F55
0x180004f20  call    cs:__imp_GetProcessHeap
0x180004f26  mov     r8, rbx; lpMem
0x180004f29  xor     edx, edx; dwFlags
0x180004f2b  mov     rcx, rax; hHeap
0x180004f2e  call    cs:__imp_HeapFree
0x180004f34  jmp     short loc_180004F55
0x180004f36  mov     rcx, rbx; pv
0x180004f39  call    cs:__imp_CoTaskMemFree
0x180004f3f  jmp     short loc_180004F55
0x180004f41  mov     rcx, rbx
0x180004f44  call    cs:__imp_AppContainerFreeMemory
0x180004f4a  jmp     short loc_180004F55
0x180004f4c  mov     rcx, rbx; hMem
0x180004f4f  call    cs:__imp_LocalFree
0x180004f55  add     rsp, 20h
0x180004f59  pop     rbx
0x180004f5a  retn
```
