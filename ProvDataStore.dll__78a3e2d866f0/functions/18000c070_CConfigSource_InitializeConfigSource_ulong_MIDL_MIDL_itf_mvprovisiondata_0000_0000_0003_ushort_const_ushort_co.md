# CConfigSource::InitializeConfigSource(ulong,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003,ushort const *,ushort const *)

- ea: `0x18000c070`
- end: `0x18000c15a`
- name: `?InitializeConfigSource@CConfigSource@@QEAAJKW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@PEBG1@Z`
- size: `234`
- prototype: `__int64 __fastcall(_DWORD *, int, int, _WORD *, _WORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b8f8`

## callees

- `0x180005644`
- `0x18000c070`

## pseudocode

```c
__int64 __fastcall CConfigSource::InitializeConfigSource(_DWORD *a1, int a2, int a3, _WORD *a4, _WORD *a5)
{
  _WORD *v5; // r11
  __int64 v6; // r8
  __int64 v7; // rdi
  __int64 v8; // r10
  __int64 v9; // rax
  _WORD *v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  _WORD *v15; // rcx
  _WORD *v16; // rdx
  int v17; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  a1[262] = a3;
  v5 = a1 + 1;
  v6 = 260;
  *a1 = a2;
  v7 = 2147483646;
  v8 = 260;
  v9 = 2147483646;
  do
  {
    if ( !v9 )
      break;
    if ( !*a4 )
      break;
    *v5++ = *a4++;
    --v9;
    --v8;
  }
  while ( v8 );
  v10 = v5 - 1;
  v11 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v10 = v5;
  *v10 = 0;
  if ( !v8 )
  {
    v12 = 268;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastore.cpp",
      (const char *)v11,
      v17);
    return v11;
  }
  v15 = a1 + 131;
  do
  {
    if ( !v7 )
      break;
    if ( !*a5 )
      break;
    *v15++ = *a5++;
    --v7;
    --v6;
  }
  while ( v6 );
  v16 = v15 - 1;
  v11 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v16 = v15;
  *v16 = 0;
  if ( !v6 )
  {
    v12 = 271;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c070  push    rbx
0x18000c072  push    rbp
0x18000c073  push    rsi
0x18000c074  push    rdi
0x18000c075  sub     rsp, 28h
0x18000c079  mov     [rcx+418h], r8d
0x18000c080  lea     r11, [rcx+4]
0x18000c084  mov     r8d, 104h
0x18000c08a  mov     [rcx], edx
0x18000c08c  mov     edi, 7FFFFFFEh
0x18000c091  mov     r10d, r8d
0x18000c094  mov     rsi, rcx
0x18000c097  mov     eax, edi
0x18000c099  xor     ebp, ebp
0x18000c09b  test    rax, rax
0x18000c09e  jz      short loc_18000C0BE
0x18000c0a0  movzx   ecx, word ptr [r9]
0x18000c0a4  test    cx, cx
0x18000c0a7  jz      short loc_18000C0BE
0x18000c0a9  mov     [r11], cx
0x18000c0ad  add     r9, 2
0x18000c0b1  add     r11, 2
0x18000c0b5  dec     rax
0x18000c0b8  sub     r10, 1
0x18000c0bc  jnz     short loc_18000C09B
0x18000c0be  mov     rax, r10
0x18000c0c1  lea     rdx, [r11-2]
0x18000c0c5  neg     rax
0x18000c0c8  mov     r9d, 8007007Ah
0x18000c0ce  sbb     ebx, ebx
0x18000c0d0  not     ebx
0x18000c0d2  and     ebx, r9d
0x18000c0d5  test    r10, r10
0x18000c0d8  cmovnz  rdx, r11
0x18000c0dc  mov     [rdx], bp
0x18000c0df  jnz     short loc_18000C0FE
0x18000c0e1  mov     edx, 10Ch; void *
0x18000c0e6  mov     rcx, [rsp+48h]; this
0x18000c0eb  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000c0f2  mov     r9d, ebx; char *
0x18000c0f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0fa  mov     eax, ebx
0x18000c0fc  jmp     short loc_18000C151
0x18000c0fe  mov     rax, [rsp+48h+arg_20]
0x18000c103  lea     rcx, [rsi+20Ch]
0x18000c10a  test    rdi, rdi
0x18000c10d  jz      short loc_18000C12B
0x18000c10f  movzx   edx, word ptr [rax]
0x18000c112  test    dx, dx
0x18000c115  jz      short loc_18000C12B
0x18000c117  mov     [rcx], dx
0x18000c11a  add     rax, 2
0x18000c11e  add     rcx, 2
0x18000c122  dec     rdi
0x18000c125  sub     r8, 1
0x18000c129  jnz     short loc_18000C10A
0x18000c12b  mov     rax, r8
0x18000c12e  lea     rdx, [rcx-2]
0x18000c132  neg     rax
0x18000c135  sbb     ebx, ebx
0x18000c137  not     ebx
0x18000c139  and     ebx, r9d
0x18000c13c  test    r8, r8
0x18000c13f  cmovnz  rdx, rcx
0x18000c143  mov     [rdx], bp
0x18000c146  jnz     short loc_18000C14F
0x18000c148  mov     edx, 10Fh
0x18000c14d  jmp     short loc_18000C0E6
0x18000c14f  xor     eax, eax
0x18000c151  add     rsp, 28h
0x18000c155  pop     rdi
0x18000c156  pop     rsi
0x18000c157  pop     rbp
0x18000c158  pop     rbx
0x18000c159  retn
```
