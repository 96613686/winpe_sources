# FxStubDriverUnloadCommon(void)

- ea: `0x140041f20`
- end: `0x140042033`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `275`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140042074`
- `0x1400421f0`

## callees

- `0x140041f20`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140041ffa`
- `ntoskrnl!DbgPrintEx` at `0x140041ffa`
- `WDFLDR!WdfVersionUnbind` at `0x14004201b`
- `WDFLDR!WdfVersionUnbind` at `0x14004201b`
- `WDFLDR!WdfVersionUnbindClass` at `0x140041fd8`
- `WDFLDR!WdfVersionUnbindClass` at `0x140041fb6`
- `WDFLDR!WdfVersionUnbindClass` at `0x140041fd8`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  __int64 *v0; // rcx
  __int64 *v1; // rdi
  __int64 *v2; // rbx
  void (__fastcall *v3)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), __int64 *, PWDF_DRIVER_GLOBALS, __int64 *); // rax

  if ( off_14005EFE8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
  {
    v0 = &NetAdapterCx_BIND_INFO;
    if ( *(_DWORD *)off_14005EFE8 == 120 )
      v1 = (__int64 *)((char *)off_14005EFE8 + 120);
    else
      v1 = (__int64 *)((char *)off_14005EFE8 + 80);
    while ( 1 )
    {
      while ( v0 + 1 <= v1 && !*v0 )
        ++v0;
      if ( v0 < v1 )
      {
        if ( (v0 + 10 > v1 || *(_DWORD *)v0 != 80) && (v0 + 15 > v1 || *(_DWORD *)v0 != 120) )
        {
LABEL_21:
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
        goto LABEL_21;
      if ( v2 >= v1 )
        break;
      v3 = (void (__fastcall *)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), __int64 *, PWDF_DRIVER_GLOBALS, __int64 *))v2[8];
      if ( v3 )
        v3(WdfVersionUnbindClass, &qword_14005E070, WdfDriverGlobals, v2);
      else
        WdfVersionUnbindClass(&qword_14005E070, WdfDriverGlobals, v2);
      v0 = (__int64 *)((char *)v2 + *(unsigned int *)v2);
    }
  }
  WdfVersionUnbind(&WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink, &qword_14005E070, WdfDriverGlobals);
}

```

## disassembly

```asm
0x140041f20  mov     [rsp+arg_0], rbx
0x140041f25  push    rdi
0x140041f26  sub     rsp, 30h
0x140041f2a  mov     rdi, cs:off_14005EFE8
0x140041f31  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140041f38  cmp     rdi, rax
0x140041f3b  jz      loc_140042006
0x140041f41  cmp     dword ptr [rdi], 78h ; 'x'
0x140041f44  lea     rcx, _NetAdapterCx_BIND_INFO
0x140041f4b  jnz     short loc_140041F53
0x140041f4d  add     rdi, 78h ; 'x'
0x140041f51  jmp     short loc_140041F63
0x140041f53  add     rdi, 50h ; 'P'
0x140041f57  jmp     short loc_140041F63
0x140041f59  cmp     qword ptr [rcx], 0
0x140041f5d  jnz     short loc_140041F6C
0x140041f5f  add     rcx, 8
0x140041f63  lea     rax, [rcx+8]
0x140041f67  cmp     rax, rdi
0x140041f6a  jbe     short loc_140041F59
0x140041f6c  cmp     rcx, rdi
0x140041f6f  jb      short loc_140041F76
0x140041f71  mov     rbx, rdi
0x140041f74  jmp     short loc_140041F95
0x140041f76  lea     rax, [rcx+50h]
0x140041f7a  cmp     rax, rdi
0x140041f7d  ja      short loc_140041F84
0x140041f7f  cmp     dword ptr [rcx], 50h ; 'P'
0x140041f82  jz      short loc_140041F92
0x140041f84  lea     rax, [rcx+78h]
0x140041f88  cmp     rax, rdi
0x140041f8b  ja      short loc_140041FEE
0x140041f8d  cmp     dword ptr [rcx], 78h ; 'x'
0x140041f90  jnz     short loc_140041FEE
0x140041f92  mov     rbx, rcx
0x140041f95  test    rbx, rbx
0x140041f98  jz      short loc_140041FEE
0x140041f9a  cmp     rbx, rdi
0x140041f9d  jnb     short loc_140042006
0x140041f9f  mov     rax, [rbx+40h]
0x140041fa3  test    rax, rax
0x140041fa6  jz      short loc_140041FC7
0x140041fa8  mov     r8, cs:WdfDriverGlobals
0x140041faf  lea     rdx, qword_14005E070
0x140041fb6  mov     rcx, cs:__imp_WdfVersionUnbindClass
0x140041fbd  mov     r9, rbx
0x140041fc0  call    _guard_dispatch_icall
0x140041fc5  jmp     short loc_140041FE4
0x140041fc7  mov     rdx, cs:WdfDriverGlobals
0x140041fce  lea     rcx, qword_14005E070
0x140041fd5  mov     r8, rbx
0x140041fd8  call    cs:__imp_WdfVersionUnbindClass
0x140041fdf  nop     dword ptr [rax+rax+00h]
0x140041fe4  mov     ecx, [rbx]
0x140041fe6  add     rcx, rbx
0x140041fe9  jmp     loc_140041F63
0x140041fee  xor     edx, edx; Level
0x140041ff0  lea     r8, aFxgetnextclass; "FxGetNextClassBindInfo failed\n"
0x140041ff7  lea     ecx, [rdx+4Dh]; ComponentId
0x140041ffa  call    cs:__imp_DbgPrintEx
0x140042001  nop     dword ptr [rax+rax+00h]
0x140042006  mov     r8, cs:WdfDriverGlobals
0x14004200d  lea     rdx, qword_14005E070
0x140042014  lea     rcx, WPP_MAIN_CB.Queue+8
0x14004201b  call    cs:__imp_WdfVersionUnbind
0x140042022  nop     dword ptr [rax+rax+00h]
0x140042027  mov     rbx, [rsp+38h+arg_0]
0x14004202c  add     rsp, 30h
0x140042030  pop     rdi
0x140042031  retn
```
