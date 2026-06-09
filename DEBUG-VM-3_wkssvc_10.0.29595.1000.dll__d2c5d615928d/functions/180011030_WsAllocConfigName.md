# WsAllocConfigName

- ea: `0x180011030`
- end: `0x1800110cb`
- name: `WsAllocConfigName`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002d530`

## callees

- `0x180007710`
- `0x180011030`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011044`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011044`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011086`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011098`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800110aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011086`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011098`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800110aa`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011074`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011074`

## string_xrefs

- `0x180011068`: `System\CurrentControlSet\Services\`
- `0x18001103a`: `ServicesActive`

## pseudocode

```c
__int64 WsAllocConfigName()
{
  __int64 v0; // rax
  const WCHAR *v1; // rbx
  __int64 result; // rax

  if ( (unsigned int)_o__wcsicmp(L"ServicesActive", L"ServicesActive") )
    return 87;
  v0 = NetpMemoryAllocate(126);
  v1 = (const WCHAR *)v0;
  if ( !v0 )
    return 8;
  _o_wcscpy_s(v0, 63, L"System\\CurrentControlSet\\Services\\");
  _o_wcscat_s(v1, 63, L"LanmanWorkstation");
  _o_wcscat_s(v1, 63, L"\\");
  _o_wcscat_s(v1, 63, L"Parameters");
  result = 0;
  RegPathToWatch = v1;
  return result;
}

```

## disassembly

```asm
0x180011030  mov     [rsp+arg_0], rbx
0x180011035  push    rdi
0x180011036  sub     rsp, 20h
0x18001103a  lea     rcx, aServicesactive; "ServicesActive"
0x180011041  mov     rdx, rcx
0x180011044  call    cs:__imp__o__wcsicmp
0x18001104a  test    eax, eax
0x18001104c  jnz     short loc_1800110BB
0x18001104e  lea     ecx, [rax+7Eh]
0x180011051  call    NetpMemoryAllocate
0x180011056  mov     rbx, rax
0x180011059  test    rax, rax
0x18001105c  jnz     short loc_180011063
0x18001105e  lea     eax, [rbx+8]
0x180011061  jmp     short loc_1800110C0
0x180011063  mov     edi, 3Fh ; '?'
0x180011068  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\"
0x18001106f  mov     edx, edi
0x180011071  mov     rcx, rbx
0x180011074  call    cs:__imp__o_wcscpy_s
0x18001107a  lea     r8, aLanmanworkstat; "LanmanWorkstation"
0x180011081  mov     edx, edi
0x180011083  mov     rcx, rbx
0x180011086  call    cs:__imp__o_wcscat_s
0x18001108c  lea     r8, Src; "\\"
0x180011093  mov     edx, edi
0x180011095  mov     rcx, rbx
0x180011098  call    cs:__imp__o_wcscat_s
0x18001109e  lea     r8, aParameters; "Parameters"
0x1800110a5  mov     edx, edi
0x1800110a7  mov     rcx, rbx
0x1800110aa  call    cs:__imp__o_wcscat_s
0x1800110b0  xor     eax, eax
0x1800110b2  mov     cs:RegPathToWatch, rbx
0x1800110b9  jmp     short loc_1800110C0
0x1800110bb  mov     eax, 57h ; 'W'
0x1800110c0  mov     rbx, [rsp+28h+arg_0]
0x1800110c5  add     rsp, 20h
0x1800110c9  pop     rdi
0x1800110ca  retn
```
