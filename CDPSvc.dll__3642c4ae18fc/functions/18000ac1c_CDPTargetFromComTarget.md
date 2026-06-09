# CDPTargetFromComTarget

- ea: `0x18000ac1c`
- end: `0x18000ad14`
- name: `CDPTargetFromComTarget`
- size: `248`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ad90`
- `0x180020ac0`
- `0x180028130`
- `0x180028a20`
- `0x180029020`
- `0x180029100`
- `0x180029580`
- `0x18002a3d0`
- `0x18002a850`
- `0x18002d2f0`
- `0x18002d3f0`

## callees

- `0x180003e60`
- `0x18000ac1c`
- `0x18000ad1c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000ac9c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000acbc`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000ac9c`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18000acbc`
- `cdp!CDPCreateAppId` at `0x18000ac62`
- `cdp!CDPCreateAppId` at `0x18000ac62`

## pseudocode

```c
__int64 __fastcall CDPTargetFromComTarget(__int64 a1, __int64 a2)
{
  const char *v4; // rbp
  const char *v5; // r8
  std::_Ref_count_base *v6; // rsi
  __int64 v7; // rcx
  _QWORD v9[2]; // [rsp+38h] [rbp-50h] BYREF
  std::_Ref_count_base *v10[2]; // [rsp+48h] [rbp-40h] BYREF

  *(_OWORD *)v10 = 0;
  v9[0] = 0;
  v9[1] = v10;
  CDPCreateAppId(
    *(unsigned int *)(a2 + 8),
    *(_QWORD *)(a2 + 16),
    *(unsigned __int16 *)(a2 + 24),
    *(_QWORD *)(a2 + 32),
    v9);
  cdp::detail::address_of<ICDPAppId>::~address_of<ICDPAppId>(v9);
  v4 = *(const char **)(a2 + 48);
  v5 = *(const char **)(a2 + 40);
  v6 = v10[0];
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v5 )
    strcpy_s((char *)(a1 + 16), 0x100u, v5);
  else
    *(_BYTE *)(a1 + 16) = 0;
  if ( v4 )
    strcpy_s((char *)(a1 + 272), 0x2Du, v4);
  else
    *(_BYTE *)(a1 + 272) = 0;
  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *(_QWORD *)(a1 + 8) = v6;
  if ( v6 )
    (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v10[1] )
    std::_Ref_count_base::_Decref(v10[1]);
  return a1;
}

```

## disassembly

```asm
0x18000ac1c  mov     r11, rsp
0x18000ac1f  mov     [r11+8], rcx
0x18000ac23  push    rbx
0x18000ac24  push    rbp
0x18000ac25  push    rsi
0x18000ac26  push    rdi
0x18000ac27  sub     rsp, 68h
0x18000ac2b  mov     rbx, rdx
0x18000ac2e  mov     rdi, rcx
0x18000ac31  xorps   xmm0, xmm0
0x18000ac34  movdqu  xmmword ptr [rsp+88h+var_40], xmm0
0x18000ac3a  mov     qword ptr [r11-50h], 0
0x18000ac42  lea     rax, [r11-40h]
0x18000ac46  mov     [r11-48h], rax
0x18000ac4a  lea     rax, [r11-50h]
0x18000ac4e  mov     [r11-68h], rax
0x18000ac52  mov     r9, [rdx+20h]
0x18000ac56  movzx   r8d, word ptr [rdx+18h]
0x18000ac5b  mov     rdx, [rdx+10h]
0x18000ac5f  mov     ecx, [rbx+8]
0x18000ac62  call    cs:__imp_CDPCreateAppId
0x18000ac68  lea     rcx, [rsp+88h+var_50]
0x18000ac6d  call    ??1?$address_of@VICDPAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAppId>::~address_of<ICDPAppId>(void)
0x18000ac72  nop
0x18000ac73  mov     rbp, [rbx+30h]
0x18000ac77  mov     r8, [rbx+28h]; Source
0x18000ac7b  mov     rsi, [rsp+88h+var_40]
0x18000ac80  mov     rax, [rbx]
0x18000ac83  mov     [rdi], rax
0x18000ac86  mov     qword ptr [rdi+8], 0
0x18000ac8e  test    r8, r8
0x18000ac91  jz      short loc_18000ACA4
0x18000ac93  lea     rcx, [rdi+10h]; Destination
0x18000ac97  mov     edx, 100h; SizeInBytes
0x18000ac9c  call    cs:__imp_strcpy_s
0x18000aca2  jmp     short loc_18000ACA8
0x18000aca4  mov     byte ptr [rdi+10h], 0
0x18000aca8  test    rbp, rbp
0x18000acab  jz      short loc_18000ACC4
0x18000acad  lea     rcx, [rdi+110h]; Destination
0x18000acb4  mov     r8, rbp; Source
0x18000acb7  mov     edx, 2Dh ; '-'; SizeInBytes
0x18000acbc  call    cs:__imp_strcpy_s
0x18000acc2  jmp     short loc_18000ACCB
0x18000acc4  mov     byte ptr [rdi+110h], 0
0x18000accb  mov     rcx, [rdi+8]
0x18000accf  test    rcx, rcx
0x18000acd2  jz      short loc_18000ACE0
0x18000acd4  mov     rax, [rcx]
0x18000acd7  mov     rax, [rax+10h]
0x18000acdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ace0  mov     [rdi+8], rsi
0x18000ace4  test    rsi, rsi
0x18000ace7  jz      short loc_18000ACF9
0x18000ace9  mov     rax, [rsi]
0x18000acec  mov     rcx, rsi
0x18000acef  mov     rax, [rax+8]
0x18000acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf8  nop
0x18000acf9  mov     rcx, [rsp+88h+var_40+8]; this
0x18000acfe  test    rcx, rcx
0x18000ad01  jz      short loc_18000AD08
0x18000ad03  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ad08  mov     rax, rdi
0x18000ad0b  add     rsp, 68h
0x18000ad0f  pop     rdi
0x18000ad10  pop     rsi
0x18000ad11  pop     rbp
0x18000ad12  pop     rbx
0x18000ad13  retn
```
