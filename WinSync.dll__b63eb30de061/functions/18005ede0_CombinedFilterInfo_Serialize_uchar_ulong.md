# CombinedFilterInfo::Serialize(uchar *,ulong *)

- ea: `0x18005ede0`
- end: `0x18005efdb`
- name: `?Serialize@CombinedFilterInfo@@UEAAJPEAEPEAK@Z`
- size: `507`
- prototype: `__int64 __fastcall(CombinedFilterInfo *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005eff0`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18004bdb0`
- `0x18005ed10`
- `0x18005ede0`
- `0x180094010`

## string_xrefs

- `0x18005ee25`: `CombinedFilterInfo::Serialize`
- `0x18005efa6`: `CombinedFilterInfo::Serialize`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::Serialize(CombinedFilterInfo *this, unsigned __int8 *a2, unsigned int *a3)
{
  PVOID *v6; // rcx
  unsigned int SerializedSize; // ebx
  unsigned int v8; // r15d
  unsigned int v9; // r14d
  __int16 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ecx
  int v13; // edi
  __int16 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // ecx
  int v17; // edi
  unsigned int v19[4]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::Serialize");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 || (SerializedSize = 0, *a3) && !a2 )
    SerializedSize = -2147467261;
  v20 = 0;
  v21 = 0;
  v19[0] = 0;
  if ( !SerializedSize )
  {
    v8 = *a3;
    SerializedSize = CombinedFilterInfo::GetSerializedSize(this, v19, &v20, &v21);
    if ( !SerializedSize )
    {
      v9 = v19[0];
      *a3 = v19[0];
      if ( v8 >= v9 )
      {
        v19[0] = v8;
        SerializedSize = FilterInfo::Serialize(this, a2, v19);
        if ( !SerializedSize )
        {
          v10 = v20;
          v11 = v19[0];
          v12 = HIWORD(v20);
          a2[v19[0]] = HIBYTE(v20);
          v13 = v11 + 4;
          a2[v11 + 3] = v10;
          a2[v11 + 2] = HIBYTE(v10);
          a2[v11 + 1] = v12;
          SerializedSize = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, unsigned int *))(**((_QWORD **)this + 5)
                                                                                                + 24LL))(
                             *((_QWORD *)this + 5),
                             &a2[(unsigned int)(v11 + 4)],
                             &v20);
          if ( !SerializedSize )
          {
            v14 = v21;
            v15 = v13 + v20;
            v16 = HIWORD(v21);
            a2[v15] = HIBYTE(v21);
            v17 = v15 + 4;
            a2[v15 + 3] = v14;
            a2[v15 + 2] = HIBYTE(v14);
            a2[v15 + 1] = v16;
            SerializedSize = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, unsigned int *))(**((_QWORD **)this + 6)
                                                                                                  + 24LL))(
                               *((_QWORD *)this + 6),
                               &a2[(unsigned int)(v15 + 4)],
                               &v21);
            if ( !SerializedSize && v17 + v21 != v9 )
              SerializedSize = -2147217379;
          }
        }
      }
      else
      {
        SerializedSize = -2147024662;
      }
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      16,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::Serialize",
      SerializedSize);
  return SerializedSize;
}

```

## disassembly

```asm
0x18005ede0  mov     [rsp-28h+arg_0], rbx
0x18005ede5  mov     [rsp-28h+arg_8], rsi
0x18005edea  push    rbp
0x18005edeb  push    rdi
0x18005edec  push    r13
0x18005edee  push    r14
0x18005edf0  push    r15
0x18005edf2  mov     rbp, rsp
0x18005edf5  sub     rsp, 40h
0x18005edf9  mov     rdi, r8
0x18005edfc  mov     rsi, rdx
0x18005edff  mov     r13, rcx
0x18005ee02  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee09  lea     rax, WPP_GLOBAL_Control
0x18005ee10  cmp     rcx, rax
0x18005ee13  jz      short loc_18005EE44
0x18005ee15  test    byte ptr [rcx+1Ch], 40h
0x18005ee19  jz      short loc_18005EE44
0x18005ee1b  cmp     byte ptr [rcx+19h], 5
0x18005ee1f  jb      short loc_18005EE44
0x18005ee21  mov     rcx, [rcx+10h]
0x18005ee25  lea     r9, aCombinedfilter_3; "CombinedFilterInfo::Serialize"
0x18005ee2c  mov     edx, 0Fh
0x18005ee31  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005ee38  call    WPP_SF_s
0x18005ee3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee44  test    rdi, rdi
0x18005ee47  jz      short loc_18005EE54
0x18005ee49  xor     ebx, ebx
0x18005ee4b  cmp     [rdi], ebx
0x18005ee4d  jz      short loc_18005EE59
0x18005ee4f  test    rsi, rsi
0x18005ee52  jnz     short loc_18005EE59
0x18005ee54  mov     ebx, 80004003h
0x18005ee59  mov     [rbp+arg_10], 0
0x18005ee60  mov     [rbp+arg_18], 0
0x18005ee67  mov     [rbp+var_10], 0
0x18005ee6e  test    ebx, ebx
0x18005ee70  jnz     loc_18005EF8A
0x18005ee76  mov     r15d, [rdi]
0x18005ee79  lea     r9, [rbp+arg_18]; unsigned int *
0x18005ee7d  lea     r8, [rbp+arg_10]; unsigned int *
0x18005ee81  mov     rcx, r13; this
0x18005ee84  lea     rdx, [rbp+var_10]; unsigned int *
0x18005ee88  call    ?GetSerializedSize@CombinedFilterInfo@@AEAAJPEAK00@Z; CombinedFilterInfo::GetSerializedSize(ulong *,ulong *,ulong *)
0x18005ee8d  mov     ebx, eax
0x18005ee8f  test    eax, eax
0x18005ee91  jnz     loc_18005EF83
0x18005ee97  mov     r14d, [rbp+var_10]
0x18005ee9b  mov     [rdi], r14d
0x18005ee9e  cmp     r15d, r14d
0x18005eea1  jnb     short loc_18005EEAD
0x18005eea3  mov     ebx, 800700EAh
0x18005eea8  jmp     loc_18005EF83
0x18005eead  lea     r8, [rbp+var_10]; unsigned int *
0x18005eeb1  mov     [rbp+var_10], r15d
0x18005eeb5  mov     rdx, rsi; unsigned __int8 *
0x18005eeb8  mov     rcx, r13; this
0x18005eebb  call    ?Serialize@FilterInfo@@UEAAJPEAEPEAK@Z; FilterInfo::Serialize(uchar *,ulong *)
0x18005eec0  mov     ebx, eax
0x18005eec2  test    eax, eax
0x18005eec4  jnz     loc_18005EF83
0x18005eeca  mov     r8d, [rbp+arg_10]
0x18005eece  mov     ecx, r8d
0x18005eed1  mov     r9d, [rbp+var_10]
0x18005eed5  shr     ecx, 10h
0x18005eed8  movzx   eax, cx
0x18005eedb  shr     ax, 8
0x18005eedf  mov     [r9+rsi], al
0x18005eee3  lea     edi, [r9+4]
0x18005eee7  movzx   eax, r8w
0x18005eeeb  mov     [r9+rsi+3], r8b
0x18005eef0  shr     ax, 8
0x18005eef4  lea     r8, [rbp+arg_10]
0x18005eef8  mov     [r9+rsi+2], al
0x18005eefd  mov     [r9+rsi+1], cl
0x18005ef02  mov     rcx, [r13+28h]
0x18005ef06  mov     edx, edi
0x18005ef08  add     rdx, rsi
0x18005ef0b  mov     rax, [rcx]
0x18005ef0e  mov     rax, [rax+18h]
0x18005ef12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef17  mov     ebx, eax
0x18005ef19  test    eax, eax
0x18005ef1b  jnz     short loc_18005EF83
0x18005ef1d  mov     r8d, [rbp+arg_18]
0x18005ef21  mov     ecx, r8d
0x18005ef24  mov     r9d, [rbp+arg_10]
0x18005ef28  add     r9d, edi
0x18005ef2b  shr     ecx, 10h
0x18005ef2e  movzx   eax, cx
0x18005ef31  shr     ax, 8
0x18005ef35  mov     [r9+rsi], al
0x18005ef39  lea     edi, [r9+4]
0x18005ef3d  movzx   eax, r8w
0x18005ef41  mov     [r9+rsi+3], r8b
0x18005ef46  shr     ax, 8
0x18005ef4a  lea     r8, [rbp+arg_18]
0x18005ef4e  mov     [r9+rsi+2], al
0x18005ef53  mov     [r9+rsi+1], cl
0x18005ef58  mov     rcx, [r13+30h]
0x18005ef5c  mov     edx, edi
0x18005ef5e  add     rdx, rsi
0x18005ef61  mov     rax, [rcx]
0x18005ef64  mov     rax, [rax+18h]
0x18005ef68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef6d  mov     ebx, eax
0x18005ef6f  test    eax, eax
0x18005ef71  jnz     short loc_18005EF83
0x18005ef73  mov     ecx, [rbp+arg_18]
0x18005ef76  mov     eax, 8004101Dh
0x18005ef7b  add     ecx, edi
0x18005ef7d  cmp     ecx, r14d
0x18005ef80  cmovnz  ebx, eax
0x18005ef83  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ef8a  lea     rax, WPP_GLOBAL_Control
0x18005ef91  cmp     rcx, rax
0x18005ef94  jz      short loc_18005EFC2
0x18005ef96  test    byte ptr [rcx+1Ch], 40h
0x18005ef9a  jz      short loc_18005EFC2
0x18005ef9c  cmp     byte ptr [rcx+19h], 5
0x18005efa0  jb      short loc_18005EFC2
0x18005efa2  mov     rcx, [rcx+10h]
0x18005efa6  lea     r9, aCombinedfilter_3; "CombinedFilterInfo::Serialize"
0x18005efad  mov     edx, 10h
0x18005efb2  mov     [rsp+40h+var_20], ebx
0x18005efb6  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005efbd  call    WPP_SF_sD
0x18005efc2  mov     rsi, [rsp+40h+arg_8]
0x18005efc7  mov     eax, ebx
0x18005efc9  mov     rbx, [rsp+40h+arg_0]
0x18005efce  add     rsp, 40h
0x18005efd2  pop     r15
0x18005efd4  pop     r14
0x18005efd6  pop     r13
0x18005efd8  pop     rdi
0x18005efd9  pop     rbp
0x18005efda  retn
```
