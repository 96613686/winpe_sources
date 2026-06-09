# FxStubDriverUnloadCommon(void)

- ea: `0x140008c5c`
- end: `0x140008d53`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `247`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008d94`
- `0x140008f10`

## callees

- `0x140008c5c`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140008d1a`
- `ntoskrnl!DbgPrintEx` at `0x140008d1a`
- `WDFLDR!WdfVersionUnbindClass` at `0x140008cfb`
- `WDFLDR!WdfVersionUnbindClass` at `0x140008cd9`
- `WDFLDR!WdfVersionUnbindClass` at `0x140008cfb`
- `WDFLDR!WdfVersionUnbind` at `0x140008d3b`
- `WDFLDR!WdfVersionUnbind` at `0x140008d3b`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  void **v0; // rcx
  void **v1; // rdi
  void **v2; // rbx
  void (__fastcall *v3)(_QWORD, _QWORD, _QWORD, _QWORD); // rax

  if ( off_140012358 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
  {
    v0 = &__KMDF_CLASS_BIND_END;
    v1 = (void **)((char *)off_140012358 + 80);
    while ( 1 )
    {
      while ( v0 + 1 <= v1 && !*v0 )
        ++v0;
      if ( v0 < v1 )
      {
        if ( v0 + 10 > v1 || *(_DWORD *)v0 != 80 )
        {
LABEL_17:
          DbgPrintEx(0x4Du, 0, "FxGetNextClassBindInfo failed\n");
          break;
        }
        v2 = v0;
      }
      else
      {
        v2 = v1;
      }
      if ( !v2 )
        goto LABEL_17;
      if ( v2 >= v1 )
        break;
      v3 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v2[8];
      if ( v3 )
        v3(WdfVersionUnbindClass, &WdfBindInfo, WdfDriverGlobals, v2);
      else
        WdfVersionUnbindClass(&WdfBindInfo, WdfDriverGlobals, v2);
      v0 = (void **)((char *)v2 + *(unsigned int *)v2);
    }
  }
  WdfVersionUnbind(&DestinationString, &WdfBindInfo, WdfDriverGlobals);
}

```

## disassembly

```asm
0x140008c5c  mov     [rsp+arg_0], rbx
0x140008c61  push    rdi
0x140008c62  sub     rsp, 30h
0x140008c66  mov     rdi, cs:off_140012358
0x140008c6d  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140008c74  cmp     rdi, rax
0x140008c77  jz      loc_140008D26
0x140008c7d  lea     rcx, ?__KMDF_CLASS_BIND_END@@3PEAXEA; void * __KMDF_CLASS_BIND_END
0x140008c84  add     rdi, 50h ; 'P'
0x140008c88  jmp     short loc_140008C94
0x140008c8a  cmp     qword ptr [rcx], 0
0x140008c8e  jnz     short loc_140008C9D
0x140008c90  add     rcx, 8
0x140008c94  lea     rax, [rcx+8]
0x140008c98  cmp     rax, rdi
0x140008c9b  jbe     short loc_140008C8A
0x140008c9d  cmp     rcx, rdi
0x140008ca0  jb      short loc_140008CA7
0x140008ca2  mov     rbx, rdi
0x140008ca5  jmp     short loc_140008CB8
0x140008ca7  lea     rax, [rcx+50h]
0x140008cab  cmp     rax, rdi
0x140008cae  ja      short loc_140008D0E
0x140008cb0  cmp     dword ptr [rcx], 50h ; 'P'
0x140008cb3  jnz     short loc_140008D0E
0x140008cb5  mov     rbx, rcx
0x140008cb8  test    rbx, rbx
0x140008cbb  jz      short loc_140008D0E
0x140008cbd  cmp     rbx, rdi
0x140008cc0  jnb     short loc_140008D26
0x140008cc2  mov     rax, [rbx+40h]
0x140008cc6  test    rax, rax
0x140008cc9  jz      short loc_140008CEA
0x140008ccb  mov     r8, cs:WdfDriverGlobals
0x140008cd2  lea     rdx, WdfBindInfo
0x140008cd9  mov     rcx, cs:__imp_WdfVersionUnbindClass
0x140008ce0  mov     r9, rbx
0x140008ce3  call    _guard_dispatch_icall
0x140008ce8  jmp     short loc_140008D07
0x140008cea  mov     rdx, cs:WdfDriverGlobals
0x140008cf1  lea     rcx, WdfBindInfo
0x140008cf8  mov     r8, rbx
0x140008cfb  call    cs:__imp_WdfVersionUnbindClass
0x140008d02  nop     dword ptr [rax+rax+00h]
0x140008d07  mov     ecx, [rbx]
0x140008d09  add     rcx, rbx
0x140008d0c  jmp     short loc_140008C94
0x140008d0e  xor     edx, edx; Level
0x140008d10  lea     r8, Format; "FxGetNextClassBindInfo failed\n"
0x140008d17  lea     ecx, [rdx+4Dh]; ComponentId
0x140008d1a  call    cs:__imp_DbgPrintEx
0x140008d21  nop     dword ptr [rax+rax+00h]
0x140008d26  mov     r8, cs:WdfDriverGlobals
0x140008d2d  lea     rdx, WdfBindInfo
0x140008d34  lea     rcx, DestinationString
0x140008d3b  call    cs:__imp_WdfVersionUnbind
0x140008d42  nop     dword ptr [rax+rax+00h]
0x140008d47  mov     rbx, [rsp+38h+arg_0]
0x140008d4c  add     rsp, 30h
0x140008d50  pop     rdi
0x140008d51  retn
```
