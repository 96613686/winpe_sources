# sub_1801CDAB4

- ea: `0x1801cdab4`
- end: `0x1801cdba5`
- name: `sub_1801CDAB4`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1801cdba8`

## callees

- `0x1801cd5e4`
- `0x1801cd82c`
- `0x1801cdab4`
- `0x1801ce930`
- `0x1801d4f90`
- `0x1801d4ffc`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1801cdb83`
- `KERNEL32!GetModuleHandleW` at `0x1801cdb83`
- `USER32!IsWindow` at `0x1801cdafe`
- `USER32!IsWindow` at `0x1801cdafe`
- `USER32!SendMessageTimeoutW` at `0x1801cdb3a`
- `USER32!SendMessageTimeoutW` at `0x1801cdb3a`

## string_xrefs

- `0x1801cdb7c`: `mso.dll`

## pseudocode

```c
HMODULE sub_1801CDAB4()
{
  __int64 v0; // rbx
  HWND v1; // rcx
  HMODULE result; // rax
  ULONG_PTR dwResult; // [rsp+50h] [rbp+8h] BYREF

  v0 = sub_1801CD5E4();
  if ( dword_18025EE9C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                   + 16LL) )
  {
    sub_1801D4FFC(&dword_18025EE9C);
    if ( dword_18025EE9C == -1 )
    {
      byte_18025EE94 = GetModuleHandleW(L"mso.dll") != 0;
      sub_1801D4F90(&dword_18025EE9C);
    }
  }
  if ( byte_18025EE94 )
    return sub_1801CE930((__int64)&qword_18022A228, 0);
  if ( !sub_1801CD82C(v0) )
    return sub_1801CE930((__int64)&qword_18022A228, 0);
  if ( !IsWindow(*(HWND *)(v0 + 16)) )
    return sub_1801CE930((__int64)&qword_18022A228, 0);
  v1 = *(HWND *)(v0 + 16);
  dwResult = 0;
  if ( !SendMessageTimeoutW(v1, 0x402u, 0, 0, 8u, 0x7530u, &dwResult) )
    return sub_1801CE930((__int64)&qword_18022A228, 0);
  result = (HMODULE)dwResult;
  if ( !dwResult )
    return sub_1801CE930((__int64)&qword_18022A228, 0);
  return result;
}

```

## disassembly

```asm
0x1801cdab4  push    rbx
0x1801cdab6  sub     rsp, 40h
0x1801cdaba  call    sub_1801CD5E4
0x1801cdabf  mov     edx, cs:TlsIndex
0x1801cdac5  mov     rbx, rax
0x1801cdac8  mov     rcx, gs:58h
0x1801cdad1  mov     eax, 10h
0x1801cdad6  mov     rcx, [rcx+rdx*8]
0x1801cdada  mov     ecx, [rcx+rax]
0x1801cdadd  cmp     cs:dword_18025EE9C, ecx
0x1801cdae3  jg      short loc_1801CDB63
0x1801cdae5  cmp     cs:byte_18025EE94, 0
0x1801cdaec  jnz     short loc_1801CDB4F
0x1801cdaee  mov     rcx, rbx
0x1801cdaf1  call    sub_1801CD82C
0x1801cdaf6  test    al, al
0x1801cdaf8  jz      short loc_1801CDB4F
0x1801cdafa  mov     rcx, [rbx+10h]; hWnd
0x1801cdafe  call    cs:IsWindow
0x1801cdb04  test    eax, eax
0x1801cdb06  jz      short loc_1801CDB4F
0x1801cdb08  mov     rcx, [rbx+10h]; hWnd
0x1801cdb0c  lea     rax, [rsp+48h+dwResult]
0x1801cdb11  mov     [rsp+48h+lpdwResult], rax; lpdwResult
0x1801cdb16  xor     r9d, r9d; lParam
0x1801cdb19  mov     [rsp+48h+uTimeout], 7530h; uTimeout
0x1801cdb21  xor     r8d, r8d; wParam
0x1801cdb24  mov     edx, 402h; Msg
0x1801cdb29  mov     [rsp+48h+fuFlags], 8; fuFlags
0x1801cdb31  mov     [rsp+48h+dwResult], 0
0x1801cdb3a  call    cs:SendMessageTimeoutW
0x1801cdb40  test    rax, rax
0x1801cdb43  jz      short loc_1801CDB4F
0x1801cdb45  mov     rax, [rsp+48h+dwResult]
0x1801cdb4a  test    rax, rax
0x1801cdb4d  jnz     short loc_1801CDB5D
0x1801cdb4f  xor     edx, edx
0x1801cdb51  lea     rcx, qword_18022A228
0x1801cdb58  call    sub_1801CE930
0x1801cdb5d  add     rsp, 40h
0x1801cdb61  pop     rbx
0x1801cdb62  retn
0x1801cdb63  lea     rcx, dword_18025EE9C
0x1801cdb6a  call    sub_1801D4FFC
0x1801cdb6f  cmp     cs:dword_18025EE9C, 0FFFFFFFFh
0x1801cdb76  jnz     loc_1801CDAE5
0x1801cdb7c  lea     rcx, aMsoDll_0; "mso.dll"
0x1801cdb83  call    cs:GetModuleHandleW
0x1801cdb89  test    rax, rax
0x1801cdb8c  lea     rcx, dword_18025EE9C
0x1801cdb93  setnz   cs:byte_18025EE94
0x1801cdb9a  call    sub_1801D4F90
0x1801cdb9f  jmp     loc_1801CDAE5
```
