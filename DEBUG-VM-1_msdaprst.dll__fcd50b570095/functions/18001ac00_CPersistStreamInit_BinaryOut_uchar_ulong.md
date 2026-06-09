# CPersistStreamInit::BinaryOut(uchar *,ulong)

- ea: `0x18001ac00`
- end: `0x18001aca7`
- name: `?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z`
- size: `167`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ce6c`
- `0x18001e10c`
- `0x18001edac`
- `0x18001f4a0`
- `0x18001f5c4`

## callees

- `0x18001ac00`
- `0x18001c6a4`

## string_xrefs

- `0x18001ac28`: `0123456789abcdefenduser\databaseaccess\src\mdac\rds\shared\foxprops\uprops.cpp`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::BinaryOut(CPersistStreamInit *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 v4; // rbx
  char v8; // r9
  __int16 v9; // r8
  __int16 Src; // [rsp+60h] [rbp+18h] BYREF
  __int16 v11; // [rsp+62h] [rbp+1Ah]
  unsigned int i; // [rsp+68h] [rbp+20h] BYREF

  result = 0;
  v4 = 0;
  for ( i = 0; (unsigned int)v4 < a3; v4 = (unsigned int)(v4 + 1) )
  {
    v8 = *((_BYTE *)this + 64);
    v9 = chHex[(unsigned __int64)a2[v4] >> 4];
    if ( v8 )
    {
      HIBYTE(Src) = chHex[a2[v4] & 0xF];
      LOBYTE(Src) = v9;
    }
    else
    {
      v11 = chHex[a2[v4] & 0xF];
      Src = v9;
    }
    result = CPersistStreamInit::Write(this, &Src, v8 != 0 ? 2 : 4, &i, 1);
    if ( (int)result < 0 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18001ac00  mov     [rsp+arg_0], rbx
0x18001ac05  mov     [rsp+arg_8], rbp
0x18001ac0a  push    rsi
0x18001ac0b  push    rdi
0x18001ac0c  push    r14
0x18001ac0e  sub     rsp, 30h
0x18001ac12  xor     eax, eax
0x18001ac14  xor     ebx, ebx
0x18001ac16  mov     [rsp+48h+arg_18], eax
0x18001ac1a  mov     edi, r8d
0x18001ac1d  mov     rbp, rdx
0x18001ac20  mov     rsi, rcx
0x18001ac23  test    r8d, r8d
0x18001ac26  jz      short loc_18001AC94
0x18001ac28  lea     r14, ?chHex@@3PADA; "0123456789abcdefenduser\\databaseaccess"...
0x18001ac2f  movzx   ecx, byte ptr [rbx+rbp]
0x18001ac33  mov     r9b, [rsi+40h]
0x18001ac37  mov     eax, ecx
0x18001ac39  and     eax, 0Fh
0x18001ac3c  shr     rcx, 4
0x18001ac40  movsx   edx, byte ptr [rax+r14]
0x18001ac45  movsx   r8d, byte ptr [rcx+r14]
0x18001ac4a  test    r9b, r9b
0x18001ac4d  jz      short loc_18001AC5A
0x18001ac4f  mov     byte ptr [rsp+48h+Src+1], dl
0x18001ac53  mov     byte ptr [rsp+48h+Src], r8b
0x18001ac58  jmp     short loc_18001AC65
0x18001ac5a  mov     [rsp+48h+arg_12], dx
0x18001ac5f  mov     [rsp+48h+Src], r8w
0x18001ac65  neg     r9b
0x18001ac68  mov     [rsp+48h+var_28], 1; bool
0x18001ac6d  lea     r9, [rsp+48h+arg_18]; unsigned int *
0x18001ac72  mov     rcx, rsi; this
0x18001ac75  sbb     r8d, r8d
0x18001ac78  lea     rdx, [rsp+48h+Src]; Src
0x18001ac7d  and     r8d, 0FFFFFFFEh
0x18001ac81  add     r8d, 4; Size
0x18001ac85  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001ac8a  test    eax, eax
0x18001ac8c  js      short loc_18001AC94
0x18001ac8e  inc     ebx
0x18001ac90  cmp     ebx, edi
0x18001ac92  jb      short loc_18001AC2F
0x18001ac94  mov     rbx, [rsp+48h+arg_0]
0x18001ac99  mov     rbp, [rsp+48h+arg_8]
0x18001ac9e  add     rsp, 30h
0x18001aca2  pop     r14
0x18001aca4  pop     rdi
0x18001aca5  pop     rsi
0x18001aca6  retn
```
