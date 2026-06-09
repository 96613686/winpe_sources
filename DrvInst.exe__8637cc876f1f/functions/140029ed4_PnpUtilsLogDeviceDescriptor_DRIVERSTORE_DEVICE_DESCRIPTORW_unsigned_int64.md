# PnpUtilsLogDeviceDescriptor(_DRIVERSTORE_DEVICE_DESCRIPTORW *,unsigned __int64)

- ea: `0x140029ed4`
- end: `0x14002a0a4`
- name: `?PnpUtilsLogDeviceDescriptor@@YAXPEAU_DRIVERSTORE_DEVICE_DESCRIPTORW@@_K@Z`
- size: `464`
- prototype: `void __fastcall(struct _DRIVERSTORE_DEVICE_DESCRIPTORW *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002c2bc`

## callees

- `0x140029ed4`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x140029f02`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029f4b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029fa1`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029ff7`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a039`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a076`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029f02`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029f4b`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029fa1`
- `DEVRTL!DevRtlWriteTextLog` at `0x140029ff7`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a039`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002a076`

## string_xrefs

- `0x140029ee6`: `Active device descriptor:`
- `0x140029f8c`: `Compatible IDs       - %ws`
- `0x14002a024`: `Installed INF        - %ws`
- `0x140029fe2`: `Location Paths       - %ws`
- `0x14002a061`: `Installed Extensions - %ws`

## pseudocode

```c
void __fastcall PnpUtilsLogDeviceDescriptor(struct _DRIVERSTORE_DEVICE_DESCRIPTORW *a1, __int64 a2)
{
  _WORD *v4; // rbx
  __int64 v5; // rax
  _WORD *v6; // rbx
  __int64 v7; // rax
  _WORD *v8; // rbx
  __int64 v9; // rax
  _WORD *v10; // rax
  _WORD *v11; // rbx
  __int64 v12; // rax

  DevRtlWriteTextLog(a2, 512, 5, "Active device descriptor:");
  v4 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    while ( *v4 )
    {
      if ( v4 == *((_WORD **)a1 + 1) )
        DevRtlWriteTextLog(a2, 512, 524293, "Hardware IDs         - %ws", *((_QWORD *)a1 + 1));
      else
        DevRtlWriteTextLog(a2, 512, 524293, "                       %ws", v4);
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v4 += v5 + 1;
    }
  }
  v6 = (_WORD *)*((_QWORD *)a1 + 2);
  if ( v6 )
  {
    while ( *v6 )
    {
      if ( v6 == *((_WORD **)a1 + 2) )
        DevRtlWriteTextLog(a2, 512, 524293, "Compatible IDs       - %ws", *((_QWORD *)a1 + 2));
      else
        DevRtlWriteTextLog(a2, 512, 524293, "                       %ws", v6);
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      v6 += v7 + 1;
    }
  }
  v8 = (_WORD *)*((_QWORD *)a1 + 3);
  if ( v8 )
  {
    while ( *v8 )
    {
      if ( v8 == *((_WORD **)a1 + 3) )
        DevRtlWriteTextLog(a2, 512, 524293, "Location Paths       - %ws", *((_QWORD *)a1 + 3));
      else
        DevRtlWriteTextLog(a2, 512, 524293, "                       %ws", v8);
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v8 += v9 + 1;
    }
  }
  v10 = (_WORD *)*((_QWORD *)a1 + 4);
  if ( v10 && *v10 )
    DevRtlWriteTextLog(a2, 512, 524293, "Installed INF        - %ws", *((_QWORD *)a1 + 4));
  v11 = (_WORD *)*((_QWORD *)a1 + 5);
  if ( v11 )
  {
    while ( *v11 )
    {
      if ( v11 == *((_WORD **)a1 + 5) )
        DevRtlWriteTextLog(a2, 512, 524293, "Installed Extensions - %ws", *((_QWORD *)a1 + 5));
      else
        DevRtlWriteTextLog(a2, 512, 524293, "                       %ws", v11);
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v11 += v12 + 1;
    }
  }
}

```

## disassembly

```asm
0x140029ed4  push    rbx
0x140029ed6  push    rbp
0x140029ed7  push    rsi
0x140029ed8  push    rdi
0x140029ed9  push    r12
0x140029edb  push    r14
0x140029edd  push    r15
0x140029edf  sub     rsp, 30h
0x140029ee3  mov     rsi, rdx
0x140029ee6  lea     r9, aActiveDeviceDe; "Active device descriptor:"
0x140029eed  mov     rdi, rcx
0x140029ef0  mov     r14d, 200h
0x140029ef6  mov     edx, r14d
0x140029ef9  mov     rcx, rsi
0x140029efc  mov     r8d, 5
0x140029f02  call    cs:__imp_DevRtlWriteTextLog
0x140029f08  mov     rbx, [rdi+8]
0x140029f0c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140029f10  xor     ebp, ebp
0x140029f12  mov     r15d, 80005h
0x140029f18  test    rbx, rbx
0x140029f1b  jz      short loc_140029F6A
0x140029f1d  jmp     short loc_140029F65
0x140029f1f  mov     rax, [rdi+8]
0x140029f23  mov     r8d, r15d
0x140029f26  mov     edx, r14d
0x140029f29  mov     rcx, rsi
0x140029f2c  cmp     rbx, rax
0x140029f2f  jnz     short loc_140029F3F
0x140029f31  mov     [rsp+68h+var_48], rax
0x140029f36  lea     r9, aHardwareIdsWs; "Hardware IDs         - %ws"
0x140029f3d  jmp     short loc_140029F4B
0x140029f3f  mov     [rsp+68h+var_48], rbx
0x140029f44  lea     r9, aWs_1; "                       %ws"
0x140029f4b  call    cs:__imp_DevRtlWriteTextLog
0x140029f51  mov     rax, r12
0x140029f54  inc     rax
0x140029f57  cmp     [rbx+rax*2], bp
0x140029f5b  jnz     short loc_140029F54
0x140029f5d  lea     rbx, [rbx+rax*2]
0x140029f61  add     rbx, 2
0x140029f65  cmp     [rbx], bp
0x140029f68  jnz     short loc_140029F1F
0x140029f6a  mov     rbx, [rdi+10h]
0x140029f6e  test    rbx, rbx
0x140029f71  jz      short loc_140029FC0
0x140029f73  jmp     short loc_140029FBB
0x140029f75  mov     rax, [rdi+10h]
0x140029f79  mov     r8d, r15d
0x140029f7c  mov     edx, r14d
0x140029f7f  mov     rcx, rsi
0x140029f82  cmp     rbx, rax
0x140029f85  jnz     short loc_140029F95
0x140029f87  mov     [rsp+68h+var_48], rax
0x140029f8c  lea     r9, aCompatibleIdsW; "Compatible IDs       - %ws"
0x140029f93  jmp     short loc_140029FA1
0x140029f95  mov     [rsp+68h+var_48], rbx
0x140029f9a  lea     r9, aWs_1; "                       %ws"
0x140029fa1  call    cs:__imp_DevRtlWriteTextLog
0x140029fa7  mov     rax, r12
0x140029faa  inc     rax
0x140029fad  cmp     [rbx+rax*2], bp
0x140029fb1  jnz     short loc_140029FAA
0x140029fb3  lea     rbx, [rbx+rax*2]
0x140029fb7  add     rbx, 2
0x140029fbb  cmp     [rbx], bp
0x140029fbe  jnz     short loc_140029F75
0x140029fc0  mov     rbx, [rdi+18h]
0x140029fc4  test    rbx, rbx
0x140029fc7  jz      short loc_14002A016
0x140029fc9  jmp     short loc_14002A011
0x140029fcb  mov     rax, [rdi+18h]
0x140029fcf  mov     r8d, r15d
0x140029fd2  mov     edx, r14d
0x140029fd5  mov     rcx, rsi
0x140029fd8  cmp     rbx, rax
0x140029fdb  jnz     short loc_140029FEB
0x140029fdd  mov     [rsp+68h+var_48], rax
0x140029fe2  lea     r9, aLocationPathsW; "Location Paths       - %ws"
0x140029fe9  jmp     short loc_140029FF7
0x140029feb  mov     [rsp+68h+var_48], rbx
0x140029ff0  lea     r9, aWs_1; "                       %ws"
0x140029ff7  call    cs:__imp_DevRtlWriteTextLog
0x140029ffd  mov     rax, r12
0x14002a000  inc     rax
0x14002a003  cmp     [rbx+rax*2], bp
0x14002a007  jnz     short loc_14002A000
0x14002a009  lea     rbx, [rbx+rax*2]
0x14002a00d  add     rbx, 2
0x14002a011  cmp     [rbx], bp
0x14002a014  jnz     short loc_140029FCB
0x14002a016  mov     rax, [rdi+20h]
0x14002a01a  test    rax, rax
0x14002a01d  jz      short loc_14002A03F
0x14002a01f  cmp     [rax], bp
0x14002a022  jz      short loc_14002A03F
0x14002a024  lea     r9, aInstalledInfWs; "Installed INF        - %ws"
0x14002a02b  mov     [rsp+68h+var_48], rax
0x14002a030  mov     r8d, r15d
0x14002a033  mov     edx, r14d
0x14002a036  mov     rcx, rsi
0x14002a039  call    cs:__imp_DevRtlWriteTextLog
0x14002a03f  mov     rbx, [rdi+28h]
0x14002a043  test    rbx, rbx
0x14002a046  jz      short loc_14002A095
0x14002a048  jmp     short loc_14002A090
0x14002a04a  mov     rax, [rdi+28h]
0x14002a04e  mov     r8d, r15d
0x14002a051  mov     edx, r14d
0x14002a054  mov     rcx, rsi
0x14002a057  cmp     rbx, rax
0x14002a05a  jnz     short loc_14002A06A
0x14002a05c  mov     [rsp+68h+var_48], rax
0x14002a061  lea     r9, aInstalledExten; "Installed Extensions - %ws"
0x14002a068  jmp     short loc_14002A076
0x14002a06a  mov     [rsp+68h+var_48], rbx
0x14002a06f  lea     r9, aWs_1; "                       %ws"
0x14002a076  call    cs:__imp_DevRtlWriteTextLog
0x14002a07c  mov     rax, r12
0x14002a07f  inc     rax
0x14002a082  cmp     [rbx+rax*2], bp
0x14002a086  jnz     short loc_14002A07F
0x14002a088  lea     rbx, [rbx+rax*2]
0x14002a08c  add     rbx, 2
0x14002a090  cmp     [rbx], bp
0x14002a093  jnz     short loc_14002A04A
0x14002a095  add     rsp, 30h
0x14002a099  pop     r15
0x14002a09b  pop     r14
0x14002a09d  pop     r12
0x14002a09f  pop     rdi
0x14002a0a0  pop     rsi
0x14002a0a1  pop     rbp
0x14002a0a2  pop     rbx
0x14002a0a3  retn
```
