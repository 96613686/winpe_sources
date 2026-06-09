# MitigationOptionsPolicy::Policy::SetOptionState(uchar,_RTL_IMAGE_MITIGATION_POLICY *,_RTL_IMAGE_MITIGATION_POLICY *)

- ea: `0x180010fe4`
- end: `0x180011020`
- name: `?SetOptionState@Policy@MitigationOptionsPolicy@@KAXEPEAT_RTL_IMAGE_MITIGATION_POLICY@@0@Z`
- size: `60`
- prototype: `void __fastcall(char, union _RTL_IMAGE_MITIGATION_POLICY *, union _RTL_IMAGE_MITIGATION_POLICY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a5f0`
- `0x180012e1c`
- `0x180012f30`

## callees

- `0x180010fe4`

## pseudocode

```c
void __fastcall MitigationOptionsPolicy::Policy::SetOptionState(
        char a1,
        union _RTL_IMAGE_MITIGATION_POLICY *a2,
        union _RTL_IMAGE_MITIGATION_POLICY *a3)
{
  if ( (a1 & 2) != 0 )
  {
    *(_QWORD *)a2 = 1;
  }
  else if ( (a1 & 4) != 0 )
  {
    *(_QWORD *)a2 = 2;
  }
  else
  {
    *(_QWORD *)a2 = 0;
  }
  *(_QWORD *)a3 = 0;
  if ( (a1 & 0x20) != 0 )
  {
    *(_QWORD *)a3 = 1;
  }
  else if ( (a1 & 0x40) != 0 )
  {
    *(_QWORD *)a3 = 2;
  }
}

```

## disassembly

```asm
0x180010fe4  mov     r10d, 1
0x180010fea  lea     r9d, [r10+1]
0x180010fee  test    r9b, cl
0x180010ff1  jnz     short loc_180011006
0x180010ff3  test    cl, 4
0x180010ff6  jz      short loc_180010FFD
0x180010ff8  mov     [rdx], r9
0x180010ffb  jmp     short loc_180011009
0x180010ffd  mov     qword ptr [rdx], 0
0x180011004  jmp     short loc_180011009
0x180011006  mov     [rdx], r10
0x180011009  xor     eax, eax
0x18001100b  mov     [r8], rax
0x18001100e  test    cl, 20h
0x180011011  jnz     short loc_18001101C
0x180011013  test    cl, 40h
0x180011016  jz      short locret_18001101F
0x180011018  mov     [r8], r9
0x18001101b  retn
0x18001101c  mov     [r8], r10
0x18001101f  retn
```
