# CommonUtil::CMpSlimShutdownEvent::Wait(void)

- ea: `0x1800e08f0`
- end: `0x1800e0946`
- name: `?Wait@CMpSlimShutdownEvent@CommonUtil@@QEBAXXZ`
- size: `86`
- prototype: `void __fastcall(CommonUtil::CMpSlimShutdownEvent *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800e07d0`

## callees

- `0x1800e0824`
- `0x1800e08f0`

## import_xrefs

- `KERNEL32!SwitchToThread` at `0x1800e090c`
- `KERNEL32!SwitchToThread` at `0x1800e0917`
- `KERNEL32!SwitchToThread` at `0x1800e092e`
- `KERNEL32!SwitchToThread` at `0x1800e090c`
- `KERNEL32!SwitchToThread` at `0x1800e0917`
- `KERNEL32!SwitchToThread` at `0x1800e092e`

## pseudocode

```c
void __fastcall CommonUtil::CMpSlimShutdownEvent::Wait(CommonUtil::CMpSlimShutdownEvent *this)
{
  unsigned __int64 i; // rdi

  for ( i = 0; i < 3; ++i )
  {
    if ( *((_BYTE *)this + 9) )
      return;
    SwitchToThread();
  }
  while ( !*((_BYTE *)this + 8) )
  {
    SwitchToThread();
    CommonUtil::CMpSlimShutdownEvent::SlowWait(this);
  }
  while ( !*((_BYTE *)this + 9) )
    SwitchToThread();
}

```

## disassembly

```asm
0x1800e08f0  mov     [rsp+arg_0], rbx
0x1800e08f5  push    rdi
0x1800e08f6  sub     rsp, 20h
0x1800e08fa  mov     rbx, rcx
0x1800e08fd  xor     edi, edi
0x1800e08ff  cmp     rdi, 3
0x1800e0903  jnb     short loc_1800E0925
0x1800e0905  mov     al, [rbx+9]
0x1800e0908  test    al, al
0x1800e090a  jnz     short loc_1800E093B
0x1800e090c  call    cs:__imp_SwitchToThread
0x1800e0912  inc     rdi
0x1800e0915  jmp     short loc_1800E08FF
0x1800e0917  call    cs:__imp_SwitchToThread
0x1800e091d  mov     rcx, rbx; this
0x1800e0920  call    ?SlowWait@CMpSlimShutdownEvent@CommonUtil@@AEBAXXZ; CommonUtil::CMpSlimShutdownEvent::SlowWait(void)
0x1800e0925  mov     al, [rbx+8]
0x1800e0928  test    al, al
0x1800e092a  jz      short loc_1800E0917
0x1800e092c  jmp     short loc_1800E0934
0x1800e092e  call    cs:__imp_SwitchToThread
0x1800e0934  mov     al, [rbx+9]
0x1800e0937  test    al, al
0x1800e0939  jz      short loc_1800E092E
0x1800e093b  mov     rbx, [rsp+28h+arg_0]
0x1800e0940  add     rsp, 20h
0x1800e0944  pop     rdi
0x1800e0945  retn
```
