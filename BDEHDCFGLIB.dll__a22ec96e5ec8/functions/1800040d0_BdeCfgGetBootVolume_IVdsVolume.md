# BdeCfgGetBootVolume(IVdsVolume * *)

- ea: `0x1800040d0`
- end: `0x18000415f`
- name: `?BdeCfgGetBootVolume@@YAJPEAPEAUIVdsVolume@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct IVdsVolume **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004900`
- `0x180004b00`
- `0x180005024`

## callees

- `0x1800040d0`
- `0x180005ce8`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall BdeCfgGetBootVolume(struct IVdsVolume **a1)
{
  unsigned int v2; // ebx
  int FirstVolume; // eax
  struct IVdsVolume *v4; // rcx
  struct IVdsVolume *v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  if ( !g_pService )
    return (unsigned int)-1063256042;
  if ( !a1 )
    return (unsigned int)-2147467261;
  *a1 = 0;
  FirstVolume = BdeCfgpFindFirstVolume(
                  (int (*)(struct IVdsVolume *, unsigned __int64))BdeCfgpFilterVolumesByFlags,
                  2u,
                  &v6);
  v2 = FirstVolume;
  if ( FirstVolume < 0 )
    goto LABEL_8;
  if ( FirstVolume == 1 )
  {
    v2 = -1063256037;
LABEL_8:
    v4 = v6;
    goto LABEL_9;
  }
  v4 = 0;
  *a1 = v6;
LABEL_9:
  if ( v4 )
    ((void (__fastcall *)(struct IVdsVolume *))v4->lpVtbl->Release)(v4);
  return v2;
}

```

## disassembly

```asm
0x1800040d0  mov     [rsp+arg_0], rbx
0x1800040d5  push    rdi
0x1800040d6  sub     rsp, 20h
0x1800040da  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x1800040e2  mov     rdi, rcx
0x1800040e5  mov     [rsp+28h+arg_8], 0
0x1800040ee  jnz     short loc_1800040F7
0x1800040f0  mov     ebx, 0C0A00016h
0x1800040f5  jmp     short loc_180004146
0x1800040f7  test    rdi, rdi
0x1800040fa  jnz     short loc_180004103
0x1800040fc  mov     ebx, 80004003h
0x180004101  jmp     short loc_180004146
0x180004103  mov     qword ptr [rcx], 0
0x18000410a  lea     r8, [rsp+28h+arg_8]; struct IVdsVolume **
0x18000410f  lea     rcx, ?BdeCfgpFilterVolumesByFlags@@YAHPEAUIVdsVolume@@_K@Z; int (*)(struct IVdsVolume *, unsigned __int64)
0x180004116  mov     edx, 2; unsigned __int64
0x18000411b  call    ?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z; BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)
0x180004120  mov     ebx, eax
0x180004122  test    eax, eax
0x180004124  js      short loc_180004130
0x180004126  cmp     eax, 1
0x180004129  jnz     short loc_180004153
0x18000412b  mov     ebx, 0C0A0001Bh
0x180004130  mov     rcx, [rsp+28h+arg_8]
0x180004135  test    rcx, rcx
0x180004138  jz      short loc_180004146
0x18000413a  mov     rax, [rcx]
0x18000413d  mov     rax, [rax+10h]
0x180004141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004146  mov     eax, ebx
0x180004148  mov     rbx, [rsp+28h+arg_0]
0x18000414d  add     rsp, 20h
0x180004151  pop     rdi
0x180004152  retn
0x180004153  mov     rax, [rsp+28h+arg_8]
0x180004158  xor     ecx, ecx
0x18000415a  mov     [rdi], rax
0x18000415d  jmp     short loc_180004135
```
