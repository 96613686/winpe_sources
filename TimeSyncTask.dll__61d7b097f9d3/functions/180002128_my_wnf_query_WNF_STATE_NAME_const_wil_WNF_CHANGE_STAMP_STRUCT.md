# my_wnf_query(_WNF_STATE_NAME const &,wil::WNF_CHANGE_STAMP_STRUCT *)

- ea: `0x180002128`
- end: `0x1800021a0`
- name: `?my_wnf_query@@YA_NAEBU_WNF_STATE_NAME@@PEAUWNF_CHANGE_STAMP_STRUCT@wil@@@Z`
- size: `120`
- prototype: `bool __fastcall(const struct _WNF_STATE_NAME *, struct wil::WNF_CHANGE_STAMP_STRUCT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002ba0`

## callees

- `0x180002128`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180002169`
- `ntdll!NtQueryWnfStateData` at `0x180002169`

## pseudocode

```c
bool __fastcall my_wnf_query(const struct _WNF_STATE_NAME *a1, struct wil::WNF_CHANGE_STAMP_STRUCT *a2)
{
  int v3; // eax
  bool result; // al
  int v5; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
    *(_DWORD *)a2 = 0;
  v6 = 0;
  v5 = 0;
  v3 = NtQueryWnfStateData(a1, 0, 0, &v5, 0, &v6) | 0x10000000;
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -805306333 )
    return 0;
  result = v5 != 0;
  if ( a2 )
    *(_DWORD *)a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180002128  push    rbx
0x18000212a  sub     rsp, 30h
0x18000212e  mov     rbx, rdx
0x180002131  test    rdx, rdx
0x180002134  jz      short loc_18000213C
0x180002136  mov     dword ptr [rdx], 0
0x18000213c  lea     rax, [rsp+38h+arg_10]
0x180002141  mov     [rsp+38h+arg_10], 0
0x180002149  mov     [rsp+38h+var_10], rax
0x18000214e  lea     r9, [rsp+38h+arg_8]
0x180002153  xor     r8d, r8d
0x180002156  mov     [rsp+38h+var_18], 0
0x18000215f  xor     edx, edx
0x180002161  mov     [rsp+38h+arg_8], 0
0x180002169  call    cs:__imp_NtQueryWnfStateData
0x18000216f  bts     eax, 1Ch
0x180002173  mov     edx, 80000000h
0x180002178  lea     ecx, [rax+rdx]
0x18000217b  test    edx, ecx
0x18000217d  jnz     short loc_18000218A
0x18000217f  cmp     eax, 0D0000023h
0x180002184  jz      short loc_18000218A
0x180002186  xor     al, al
0x180002188  jmp     short loc_18000219A
0x18000218a  mov     ecx, [rsp+38h+arg_8]
0x18000218e  test    ecx, ecx
0x180002190  setnz   al
0x180002193  test    rbx, rbx
0x180002196  jz      short loc_18000219A
0x180002198  mov     [rbx], ecx
0x18000219a  add     rsp, 30h
0x18000219e  pop     rbx
0x18000219f  retn
```
