# AhcApiRemove

- ea: `0x14002b850`
- end: `0x14002b947`
- name: `AhcApiRemove`
- size: `247`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400497bc`

## callees

- `0x140003418`
- `0x140027bc8`
- `0x14002b850`
- `0x14003e364`
- `0x14004b2b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002b91e`
- `ntoskrnl!ZwClose` at `0x14002b91e`

## string_xrefs

- `0x14002b8a6`: `AhcApiRemove`
- `0x14002b8d2`: `AhcApiRemove`
- `0x14002b8df`: `Failed to update cache [%x]`
- `0x14002b8f3`: `Removed key: %ws`

## pseudocode

```c
__int64 __fastcall AhcApiRemove(int a1, __int64 a2)
{
  int Key; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  void *v8; // [rsp+20h] [rbp-28h]
  __int64 v9; // [rsp+20h] [rbp-28h]
  int v10[4]; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF

  v8 = *(void **)(a2 + 24);
  Handle = 0;
  *(_OWORD *)v10 = 0;
  Key = AhcpApiGetKey((int)v10, (int)&Handle, (int)a2 + 8, (int)a2 + 32, v8);
  v4 = Key;
  if ( Key < 0 )
  {
    v5 = "Failed to get key [%x]";
    v6 = 499;
LABEL_3:
    LODWORD(v9) = Key;
    AslLogCallPrintf(1, "AhcApiRemove", v6, v5, v9);
    goto LABEL_7;
  }
  Key = AhcCacheRemove(a1, (int)v10);
  v4 = Key;
  if ( Key < 0 )
  {
    v5 = "Failed to update cache [%x]";
    v6 = 509;
    goto LABEL_3;
  }
  AslLogCallPrintf(3, "AhcApiRemove", 513, "Removed key: %ws", *(_QWORD *)&v10[2]);
  v4 = 0;
LABEL_7:
  if ( Handle )
    ZwClose(Handle);
  AslAnsiStringFree(v10);
  return v4;
}

```

## disassembly

```asm
0x14002b850  mov     r11, rsp
0x14002b853  mov     [r11+8], rbx
0x14002b857  mov     [r11+18h], rbp
0x14002b85b  push    rsi
0x14002b85c  sub     rsp, 40h
0x14002b860  mov     rax, [rdx+18h]
0x14002b864  lea     r9, [rdx+20h]; int
0x14002b868  mov     rsi, rdx
0x14002b86b  mov     [r11-28h], rax
0x14002b86f  mov     rbp, rcx
0x14002b872  mov     qword ptr [r11+10h], 0
0x14002b87a  xorps   xmm0, xmm0
0x14002b87d  lea     r8, [rdx+8]; int
0x14002b881  lea     rdx, [r11+10h]; int
0x14002b885  lea     rcx, [r11-18h]; int
0x14002b889  movups  xmmword ptr [rsp+48h+var_18], xmm0
0x14002b88e  call    AhcpApiGetKey
0x14002b893  mov     ebx, eax
0x14002b895  test    eax, eax
0x14002b897  jns     short loc_14002B8BD
0x14002b899  lea     r9, aFailedToGetKey_0; "Failed to get key [%x]"
0x14002b8a0  mov     r8d, 1F3h
0x14002b8a6  lea     rdx, aAhcapiremove; "AhcApiRemove"
0x14002b8ad  mov     ecx, 1
0x14002b8b2  mov     dword ptr [rsp+48h+var_28], eax
0x14002b8b6  call    AslLogCallPrintf
0x14002b8bb  jmp     short loc_14002B911
0x14002b8bd  mov     r9d, [rsi]
0x14002b8c0  lea     rdx, [rsp+48h+var_18]; int
0x14002b8c5  mov     r8, [rsp+48h+Handle]
0x14002b8ca  mov     rcx, rbp; int
0x14002b8cd  call    AhcCacheRemove
0x14002b8d2  lea     rdx, aAhcapiremove; "AhcApiRemove"
0x14002b8d9  mov     ebx, eax
0x14002b8db  test    eax, eax
0x14002b8dd  jns     short loc_14002B8EE
0x14002b8df  lea     r9, aFailedToUpdate_1; "Failed to update cache [%x]"
0x14002b8e6  mov     r8d, 1FDh
0x14002b8ec  jmp     short loc_14002B8AD
0x14002b8ee  mov     rax, qword ptr [rsp+48h+var_18+8]
0x14002b8f3  lea     r9, aRemovedKeyWs; "Removed key: %ws"
0x14002b8fa  mov     r8d, 201h
0x14002b900  mov     [rsp+48h+var_28], rax
0x14002b905  mov     ecx, 3
0x14002b90a  call    AslLogCallPrintf
0x14002b90f  xor     ebx, ebx
0x14002b911  cmp     [rsp+48h+Handle], 0
0x14002b917  jz      short loc_14002B92A
0x14002b919  mov     rcx, [rsp+48h+Handle]; Handle
0x14002b91e  call    cs:__imp_ZwClose
0x14002b925  nop     dword ptr [rax+rax+00h]
0x14002b92a  lea     rcx, [rsp+48h+var_18]
0x14002b92f  call    AslAnsiStringFree
0x14002b934  mov     rbp, [rsp+48h+arg_10]
0x14002b939  mov     eax, ebx
0x14002b93b  mov     rbx, [rsp+48h+arg_0]
0x14002b940  add     rsp, 40h
0x14002b944  pop     rsi
0x14002b945  retn
```
