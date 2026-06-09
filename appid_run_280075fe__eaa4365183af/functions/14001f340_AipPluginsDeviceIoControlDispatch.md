# AipPluginsDeviceIoControlDispatch

- ea: `0x14001f340`
- end: `0x14001f3b2`
- name: `AipPluginsDeviceIoControlDispatch`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140033f50`

## callees

- `0x14001f340`
- `0x1400218c0`

## pseudocode

```c
__int64 __fastcall AipPluginsDeviceIoControlDispatch(__int64 a1)
{
  __int64 i; // rdi
  int v3; // ecx
  __int64 result; // rax

  *(_DWORD *)(a1 + 72) = 0;
  for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
  {
    v3 = AipPluginInvokeIoctlCallback((__int64)&qword_140009040[9 * i], &qword_1400192B0[i], a1);
    if ( v3 < 0 )
      goto LABEL_6;
  }
  v3 = 0;
LABEL_6:
  result = 3221225488LL;
  if ( *(_DWORD *)(a1 + 72) )
    return (unsigned int)v3;
  return result;
}

```

## disassembly

```asm
0x14001f340  mov     [rsp+arg_0], rbx
0x14001f345  mov     [rsp+arg_8], rsi
0x14001f34a  push    rdi
0x14001f34b  sub     rsp, 20h
0x14001f34f  mov     rbx, rcx
0x14001f352  mov     dword ptr [rcx+48h], 0
0x14001f359  xor     edi, edi
0x14001f35b  lea     rsi, cs:140000000h
0x14001f362  cmp     edi, 4
0x14001f365  jnb     short loc_14001F393
0x14001f367  lea     rax, [rdi+rdi*8]
0x14001f36b  mov     r8, rbx
0x14001f36e  lea     rdx, rva qword_1400192B0[rsi]
0x14001f375  lea     rcx, rva qword_140009040[rsi]
0x14001f37c  lea     rdx, [rdx+rdi*8]
0x14001f380  lea     rcx, [rcx+rax*8]
0x14001f384  call    AipPluginInvokeIoctlCallback
0x14001f389  mov     ecx, eax
0x14001f38b  test    eax, eax
0x14001f38d  js      short loc_14001F395
0x14001f38f  inc     edi
0x14001f391  jmp     short loc_14001F362
0x14001f393  xor     ecx, ecx
0x14001f395  cmp     dword ptr [rbx+48h], 0
0x14001f399  mov     eax, 0C0000010h
0x14001f39e  mov     rbx, [rsp+28h+arg_0]
0x14001f3a3  mov     rsi, [rsp+28h+arg_8]
0x14001f3a8  cmovnz  eax, ecx
0x14001f3ab  add     rsp, 20h
0x14001f3af  pop     rdi
0x14001f3b0  retn
```
