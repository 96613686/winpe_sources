# wdmPnpUpdateDriver(ulong,ushort const *,unsigned __int64,ulong)

- ea: `0x1800023f0`
- end: `0x180002459`
- name: `?wdmPnpUpdateDriver@@YAXKPEBG_KK@Z`
- size: `105`
- prototype: `void(unsigned int, const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180001660`

## callees

- `0x1800023f0`
- `0x180002460`
- `0x180002558`
- `0x180002718`

## pseudocode

```c
void __fastcall wdmPnpUpdateDriver(int a1, const unsigned __int16 *a2, __int64 a3, unsigned int a4)
{
  const unsigned __int16 *v6; // rax
  const unsigned __int16 *v7; // rdi
  int v8; // ebx
  unsigned int v9; // edx

  v6 = wdmDevInterfaceInstall(a2, a3, a4);
  v7 = v6;
  if ( v6 )
  {
    v8 = a1 - 0x8000;
    if ( v8 )
    {
      if ( v8 != 4 )
        goto LABEL_5;
      v9 = 0x2000;
    }
    else
    {
      v9 = 0;
    }
    wdmDriverLoadAllClasses(v6, v9, a4);
LABEL_5:
    wdmDevInterfaceDec(v7);
  }
}

```

## disassembly

```asm
0x1800023f0  mov     [rsp+arg_0], rbx
0x1800023f5  mov     [rsp+arg_8], rsi
0x1800023fa  push    rdi
0x1800023fb  sub     rsp, 20h
0x1800023ff  mov     rax, r8
0x180002402  mov     r10, rdx
0x180002405  mov     ebx, ecx
0x180002407  mov     rdx, rax; unsigned __int64
0x18000240a  mov     rcx, r10; unsigned __int16 *
0x18000240d  mov     r8d, r9d; unsigned int
0x180002410  mov     esi, r9d
0x180002413  call    ?wdmDevInterfaceInstall@@YAPEBGPEBG_KK@Z; wdmDevInterfaceInstall(ushort const *,unsigned __int64,ulong)
0x180002418  mov     rdi, rax
0x18000241b  test    rax, rax
0x18000241e  jz      short loc_18000243D
0x180002420  sub     ebx, 8000h
0x180002426  jnz     short loc_18000244D
0x180002428  xor     edx, edx; unsigned int
0x18000242a  mov     r8d, esi; unsigned int
0x18000242d  mov     rcx, rdi; unsigned __int16 *
0x180002430  call    ?wdmDriverLoadAllClasses@@YAXPEBGII@Z; wdmDriverLoadAllClasses(ushort const *,uint,uint)
0x180002435  mov     rcx, rdi
0x180002438  call    wdmDevInterfaceDec
0x18000243d  mov     rbx, [rsp+28h+arg_0]
0x180002442  mov     rsi, [rsp+28h+arg_8]
0x180002447  add     rsp, 20h
0x18000244b  pop     rdi
0x18000244c  retn
0x18000244d  cmp     ebx, 4
0x180002450  jnz     short loc_180002435
0x180002452  mov     edx, 2000h
0x180002457  jmp     short loc_18000242A
```
