# MbbNdisGetReadyInfo(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x140011560`
- end: `0x1400115b3`
- name: `?MbbNdisGetReadyInfo@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `83`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140011560`
- `0x14001fc2c`

## pseudocode

```c
__int64 __fastcall MbbNdisGetReadyInfo(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  int v4; // eax
  unsigned __int8 *v5; // rdx
  unsigned int v6; // r8d
  int v8; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_WORD *)(**((_QWORD **)a1 + 6) + 82LL) < 0x400u )
  {
    v6 = 0;
    v5 = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 53) || *((_BYTE *)a1 + 576) )
      v4 = *((_DWORD *)a2 + 1);
    else
      v4 = -1;
    v8 = v4;
    v5 = (unsigned __int8 *)&v8;
    v6 = 4;
  }
  return MbbUtilQueryAttributeWithParameter(a1, v5, v6);
}

```

## disassembly

```asm
0x140011560  sub     rsp, 28h
0x140011564  mov     rax, [rcx+30h]
0x140011568  mov     r8, [rax]
0x14001156b  mov     eax, 400h
0x140011570  cmp     [r8+52h], ax
0x140011575  jb      short loc_1400115A3
0x140011577  cmp     qword ptr [rcx+1A8h], 0
0x14001157f  jnz     short loc_14001158F
0x140011581  cmp     byte ptr [rcx+240h], 0
0x140011588  jnz     short loc_14001158F
0x14001158a  or      eax, 0FFFFFFFFh
0x14001158d  jmp     short loc_140011592
0x14001158f  mov     eax, [rdx+4]
0x140011592  mov     [rsp+28h+arg_0], eax
0x140011596  lea     rdx, [rsp+28h+arg_0]
0x14001159b  mov     r8d, 4
0x1400115a1  jmp     short loc_1400115A8
0x1400115a3  xor     r8d, r8d; unsigned int
0x1400115a6  xor     edx, edx; unsigned __int8 *
0x1400115a8  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x1400115ad  add     rsp, 28h
0x1400115b1  retn
```
