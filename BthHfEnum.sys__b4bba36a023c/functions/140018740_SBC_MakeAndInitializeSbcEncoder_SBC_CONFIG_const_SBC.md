# SBC::MakeAndInitializeSbcEncoder(SBC_CONFIG const &,SBC * *)

- ea: `0x140018740`
- end: `0x1400187c8`
- name: `?MakeAndInitializeSbcEncoder@SBC@@SAJAEBUSBC_CONFIG@@PEAPEAV1@@Z`
- size: `136`
- prototype: `__int64 __fastcall(const struct SBC_CONFIG *, struct SBC **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140017988`

## callees

- `0x140015d00`
- `0x140018094`
- `0x140018740`
- `0x14001b2c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001876c`
- `ntoskrnl!ExAllocatePool2` at `0x14001876c`

## pseudocode

```c
__int64 __fastcall SBC::MakeAndInitializeSbcEncoder(const struct SBC_CONFIG *a1, struct SBC **a2)
{
  SBC *Pool2; // rax
  SBC *v5; // rbx
  int v6; // edi

  *a2 = 0;
  Pool2 = (SBC *)ExAllocatePool2(64, 5416, 1684882288);
  v5 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x1528u);
    v6 = SBC::ConfigEncode(v5, a1);
    if ( v6 < 0 )
      operator delete(v5);
    else
      *a2 = v5;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140018740  mov     [rsp+arg_0], rbx
0x140018745  mov     [rsp+arg_8], rsi
0x14001874a  push    rdi
0x14001874b  sub     rsp, 20h
0x14001874f  mov     rsi, rdx
0x140018752  mov     qword ptr [rdx], 0
0x140018759  mov     rdi, rcx
0x14001875c  mov     edx, 1528h
0x140018761  mov     ecx, 40h ; '@'
0x140018766  mov     r8d, 646D4370h
0x14001876c  call    cs:__imp_ExAllocatePool2
0x140018773  nop     dword ptr [rax+rax+00h]
0x140018778  mov     rbx, rax
0x14001877b  test    rax, rax
0x14001877e  jz      short loc_1400187B0
0x140018780  xor     edx, edx; Val
0x140018782  mov     r8d, 1528h; Size
0x140018788  mov     rcx, rax; void *
0x14001878b  call    memset
0x140018790  mov     rdx, rdi; struct SBC_CONFIG *
0x140018793  mov     rcx, rbx; this
0x140018796  call    ?ConfigEncode@SBC@@QEAAJAEBUSBC_CONFIG@@_N@Z; SBC::ConfigEncode(SBC_CONFIG const &,bool)
0x14001879b  mov     edi, eax
0x14001879d  test    eax, eax
0x14001879f  js      short loc_1400187A6
0x1400187a1  mov     [rsi], rbx
0x1400187a4  jmp     short loc_1400187B5
0x1400187a6  mov     rcx, rbx; void *
0x1400187a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400187ae  jmp     short loc_1400187B5
0x1400187b0  mov     edi, 0C000009Ah
0x1400187b5  mov     rbx, [rsp+28h+arg_0]
0x1400187ba  mov     eax, edi
0x1400187bc  mov     rsi, [rsp+28h+arg_8]
0x1400187c1  add     rsp, 20h
0x1400187c5  pop     rdi
0x1400187c6  retn
```
