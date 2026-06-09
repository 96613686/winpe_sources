# InitializeConfigurationGlobals

- ea: `0x180004380`
- end: `0x1800043f2`
- name: `InitializeConfigurationGlobals`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800035d0`

## callees

- `0x180004090`
- `0x180004380`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043d8`

## pseudocode

```c
__int64 InitializeConfigurationGlobals()
{
  __int64 result; // rax
  unsigned int v1; // ebx

  result = HttpApiCreateHandleHelper((int)&g_ServiceCommChannelHandle, 2u, -1072693248, 0, 0, 0, 2u, 0, 0, 0, 0);
  v1 = result;
  if ( (_DWORD)result )
  {
    if ( g_ServiceCommChannelHandle )
    {
      CloseHandle(g_ServiceCommChannelHandle);
      result = v1;
      g_ServiceCommChannelHandle = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004380  mov     rax, rsp
0x180004383  mov     [rax+10h], rbx
0x180004387  push    rdi
0x180004388  sub     rsp, 60h
0x18000438c  xor     edi, edi
0x18000438e  mov     ecx, 2
0x180004393  mov     [rax-18h], rdi
0x180004397  mov     edx, ecx; int
0x180004399  mov     [rax-20h], edi
0x18000439c  xor     r9d, r9d; int
0x18000439f  mov     [rax-28h], rdi
0x1800043a3  mov     r8d, 0C0100000h; int
0x1800043a9  mov     [rax-30h], edi
0x1800043ac  mov     [rax-38h], ecx
0x1800043af  mov     [rsp+68h+arg_0], ecx
0x1800043b3  lea     rcx, g_ServiceCommChannelHandle; int
0x1800043ba  mov     [rax-40h], edi
0x1800043bd  mov     [rax-48h], rdi
0x1800043c1  call    HttpApiCreateHandleHelper
0x1800043c6  mov     ebx, eax
0x1800043c8  test    eax, eax
0x1800043ca  jz      short loc_1800043E7
0x1800043cc  mov     rcx, cs:g_ServiceCommChannelHandle; hObject
0x1800043d3  test    rcx, rcx
0x1800043d6  jz      short loc_1800043E7
0x1800043d8  call    cs:__imp_CloseHandle
0x1800043de  mov     eax, ebx
0x1800043e0  mov     cs:g_ServiceCommChannelHandle, rdi
0x1800043e7  mov     rbx, [rsp+68h+arg_8]
0x1800043ec  add     rsp, 60h
0x1800043f0  pop     rdi
0x1800043f1  retn
```
