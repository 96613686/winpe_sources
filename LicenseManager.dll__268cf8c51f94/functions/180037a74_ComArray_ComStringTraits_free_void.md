# ComArray<ComStringTraits>::_free(void)

- ea: `0x180037a74`
- end: `0x180037ace`
- name: `?_free@?$ComArray@UComStringTraits@@@@AEAAXXZ`
- size: `90`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800377fc`
- `0x180055e28`
- `0x18006cf4c`
- `0x180071e78`
- `0x1800734c0`
- `0x18008afe0`
- `0x18009685c`

## callees

- `0x180037a74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ab0`

## pseudocode

```c
void __fastcall ComArray<ComStringTraits>::_free(LPVOID *a1)
{
  _DWORD *v1; // rsi
  __int64 i; // rbp
  _QWORD *v4; // rbx

  v1 = a1 + 1;
  if ( *a1 )
  {
    for ( i = 0; (unsigned int)i < *v1; i = (unsigned int)(i + 1) )
    {
      v4 = *a1;
      CoTaskMemFree(*((LPVOID *)*a1 + i));
      v4[i] = 0;
    }
    CoTaskMemFree(*a1);
    *a1 = 0;
  }
  *v1 = 0;
}

```

## disassembly

```asm
0x180037a74  push    rbx
0x180037a76  push    rbp
0x180037a77  push    rsi
0x180037a78  push    rdi
0x180037a79  push    r14
0x180037a7b  sub     rsp, 20h
0x180037a7f  cmp     qword ptr [rcx], 0
0x180037a83  lea     rsi, [rcx+8]
0x180037a87  mov     r14, rcx
0x180037a8a  jz      short loc_180037ABD
0x180037a8c  xor     ebp, ebp
0x180037a8e  cmp     [rsi], ebp
0x180037a90  jbe     short loc_180037AAD
0x180037a92  mov     rbx, [r14]
0x180037a95  mov     rcx, [rbx+rbp*8]; pv
0x180037a99  call    cs:__imp_CoTaskMemFree
0x180037a9f  mov     qword ptr [rbx+rbp*8], 0
0x180037aa7  inc     ebp
0x180037aa9  cmp     ebp, [rsi]
0x180037aab  jb      short loc_180037A92
0x180037aad  mov     rcx, [r14]; pv
0x180037ab0  call    cs:__imp_CoTaskMemFree
0x180037ab6  mov     qword ptr [r14], 0
0x180037abd  mov     dword ptr [rsi], 0
0x180037ac3  add     rsp, 20h
0x180037ac7  pop     r14
0x180037ac9  pop     rdi
0x180037aca  pop     rsi
0x180037acb  pop     rbp
0x180037acc  pop     rbx
0x180037acd  retn
```
