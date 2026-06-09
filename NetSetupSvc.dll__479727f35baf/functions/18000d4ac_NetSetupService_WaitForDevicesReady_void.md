# NetSetupService::WaitForDevicesReady(void)

- ea: `0x18000d4ac`
- end: `0x18000d533`
- name: `?WaitForDevicesReady@NetSetupService@@QEAAXXZ`
- size: `135`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000affc`
- `0x180013230`
- `0x1800137fc`

## callees

- `0x1800078d0`
- `0x18000d4ac`
- `0x180026470`

## pseudocode

```c
void __fastcall NetSetupService::WaitForDevicesReady(NetSetupService *this)
{
  Event *v1; // rbx

  v1 = (NetSetupService *)((char *)this + 88);
  if ( !Event::WaitFor((NetSetupService *)((char *)this + 88), 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids);
    Event::WaitFor(v1, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids);
  }
}

```

## disassembly

```asm
0x18000d4ac  mov     [rsp+arg_0], rbx
0x18000d4b1  push    rdi
0x18000d4b2  sub     rsp, 20h
0x18000d4b6  lea     rbx, [rcx+58h]
0x18000d4ba  xor     edx, edx; unsigned int
0x18000d4bc  mov     rcx, rbx; this
0x18000d4bf  call    ?WaitFor@Event@@QEAA_NK@Z; Event::WaitFor(ulong)
0x18000d4c4  test    al, al
0x18000d4c6  jnz     short loc_18000D528
0x18000d4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4cf  lea     rdi, WPP_GLOBAL_Control
0x18000d4d6  cmp     rcx, rdi
0x18000d4d9  jz      short loc_18000D4F6
0x18000d4db  cmp     byte ptr [rcx+19h], 4
0x18000d4df  jb      short loc_18000D4F6
0x18000d4e1  mov     rcx, [rcx+10h]
0x18000d4e5  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000d4ec  mov     edx, 0Dh
0x18000d4f1  call    WPP_SF_
0x18000d4f6  or      edx, 0FFFFFFFFh; unsigned int
0x18000d4f9  mov     rcx, rbx; this
0x18000d4fc  call    ?WaitFor@Event@@QEAA_NK@Z; Event::WaitFor(ulong)
0x18000d501  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d508  cmp     rcx, rdi
0x18000d50b  jz      short loc_18000D528
0x18000d50d  cmp     byte ptr [rcx+19h], 4
0x18000d511  jb      short loc_18000D528
0x18000d513  mov     rcx, [rcx+10h]
0x18000d517  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000d51e  mov     edx, 0Eh
0x18000d523  call    WPP_SF_
0x18000d528  mov     rbx, [rsp+28h+arg_0]
0x18000d52d  add     rsp, 20h
0x18000d531  pop     rdi
0x18000d532  retn
```
