# CloseAdminBaseKey(IMSAdminBaseW *,ulong)

- ea: `0x180012ffc`
- end: `0x180013019`
- name: `?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z`
- size: `29`
- prototype: `void __fastcall(struct IMSAdminBaseW *, unsigned int)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dbc`
- `0x1800049c0`
- `0x180005830`
- `0x180005a00`
- `0x180005cd0`
- `0x180006090`
- `0x180006240`
- `0x180006660`
- `0x180006894`
- `0x1800085a0`
- `0x18000a164`
- `0x18000a860`
- `0x18000aa70`
- `0x18000ad88`
- `0x18000b2b0`
- `0x18000d83c`
- `0x180013fd0`
- `0x180015664`

## callees

- `0x180012ffc`
- `0x18001e010`

## pseudocode

```c
void __fastcall CloseAdminBaseKey(struct IMSAdminBaseW *a1)
{
  if ( a1 )
    ((void (__fastcall *)(struct IMSAdminBaseW *))a1->lpVtbl->CloseKey)(a1);
}

```

## disassembly

```asm
0x180012ffc  sub     rsp, 28h
0x180013000  test    rcx, rcx
0x180013003  jz      short loc_180013014
0x180013005  mov     rax, [rcx]
0x180013008  mov     rax, [rax+90h]
0x18001300f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013014  add     rsp, 28h
0x180013018  retn
```
