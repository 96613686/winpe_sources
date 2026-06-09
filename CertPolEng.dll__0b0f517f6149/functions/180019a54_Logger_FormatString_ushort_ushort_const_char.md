# Logger::FormatString(ushort * &,ushort const *,char *)

- ea: `0x180019a54`
- end: `0x180019b1c`
- name: `?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z`
- size: `200`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, char *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180009424`
- `0x18000aa90`
- `0x18000b32c`
- `0x18000b3c4`

## callees

- `0x1800088f0`
- `0x1800181e8`
- `0x1800191d0`
- `0x180019384`
- `0x180019a54`
- `0x180019b24`

## pseudocode

```c
__int64 __fastcall Logger::FormatString(unsigned __int16 **a1, const unsigned __int16 *a2, char *a3)
{
  __int64 result; // rax
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  unsigned __int16 **v9; // r8
  unsigned __int64 *v10; // r9
  unsigned __int64 v11; // rdx
  unsigned int v12; // [rsp+20h] [rbp-48h]
  unsigned __int64 i; // [rsp+78h] [rbp+10h] BYREF

  i = 0;
  if ( !a2 )
    return 2147942487LL;
  result = StringCchLengthW(a2, (unsigned __int64)a2, &i);
  if ( (int)result >= 0 )
  {
    v7 = i + 50;
LABEL_5:
    for ( i = v7; ; v7 = i )
    {
      v8 = (unsigned __int16 *)SafeAlloc(2 * v7);
      *a1 = v8;
      if ( !v8 )
        break;
      result = StringCchVPrintfExW(v8, v7, v9, v10, v12, a2, a3);
      if ( (_DWORD)result != -2147024774 )
        return result;
      SafeFree(*a1);
      *a1 = 0;
      if ( v7 >= 0x3FFFFFFF )
      {
        if ( v7 == 0x7FFFFFFF )
          return 2147942414LL;
        v7 = 0x7FFFFFFF;
        goto LABEL_5;
      }
      result = ULongLongMult(v7, v11, &i);
      if ( (int)result < 0 )
        return result;
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180019a54  push    rbx
0x180019a56  push    rbp
0x180019a57  push    rsi
0x180019a58  push    rdi
0x180019a59  sub     rsp, 48h
0x180019a5d  mov     [rsp+68h+arg_8], 0
0x180019a66  mov     rbp, r8
0x180019a69  mov     rsi, rdx
0x180019a6c  mov     rdi, rcx
0x180019a6f  test    rdx, rdx
0x180019a72  jnz     short loc_180019A7E
0x180019a74  mov     eax, 80070057h
0x180019a79  jmp     loc_180019B13
0x180019a7e  lea     r8, [rsp+68h+arg_8]; unsigned __int64 *
0x180019a83  mov     rcx, rsi; unsigned __int16 *
0x180019a86  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180019a8b  test    eax, eax
0x180019a8d  js      loc_180019B13
0x180019a93  mov     rbx, [rsp+68h+arg_8]
0x180019a98  add     rbx, 32h ; '2'
0x180019a9c  mov     [rsp+68h+arg_8], rbx
0x180019aa1  lea     rcx, [rbx+rbx]; unsigned __int64
0x180019aa5  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180019aaa  mov     [rdi], rax
0x180019aad  test    rax, rax
0x180019ab0  jz      short loc_180019B0E
0x180019ab2  mov     [rsp+68h+var_38], rbp; char *
0x180019ab7  mov     rdx, rbx; unsigned __int64
0x180019aba  mov     rcx, rax; Buffer
0x180019abd  mov     [rsp+68h+var_40], rsi; unsigned __int16 *
0x180019ac2  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x180019ac7  cmp     eax, 8007007Ah
0x180019acc  jnz     short loc_180019B13
0x180019ace  mov     rcx, [rdi]; void *
0x180019ad1  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180019ad6  mov     qword ptr [rdi], 0
0x180019add  cmp     rbx, 3FFFFFFFh
0x180019ae4  jb      short loc_180019AF6
0x180019ae6  cmp     rbx, 7FFFFFFFh
0x180019aed  jz      short loc_180019B0E
0x180019aef  mov     ebx, 7FFFFFFFh
0x180019af4  jmp     short loc_180019A9C
0x180019af6  lea     r8, [rsp+68h+arg_8]; unsigned __int64 *
0x180019afb  mov     rcx, rbx; unsigned __int64
0x180019afe  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180019b03  test    eax, eax
0x180019b05  js      short loc_180019B13
0x180019b07  mov     rbx, [rsp+68h+arg_8]
0x180019b0c  jmp     short loc_180019AA1
0x180019b0e  mov     eax, 8007000Eh
0x180019b13  add     rsp, 48h
0x180019b17  pop     rdi
0x180019b18  pop     rsi
0x180019b19  pop     rbp
0x180019b1a  pop     rbx
0x180019b1b  retn
```
