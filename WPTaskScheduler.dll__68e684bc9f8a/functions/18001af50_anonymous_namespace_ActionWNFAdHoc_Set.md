# _anonymous_namespace_::ActionWNFAdHoc::Set

- ea: `0x18001af50`
- end: `0x18001b0ff`
- name: `_anonymous_namespace_::ActionWNFAdHoc::Set`
- size: `431`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, __int128 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x18000e970`
- `0x18000ea40`
- `0x18001aba0`
- `0x18001af50`
- `0x18001b178`
- `0x18001f4dc`
- `0x180020a64`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x18001b04c`
- `msvcrt!free` at `0x18001b04c`
- `ntdll!NtCreateWnfStateName` at `0x18001b03a`
- `ntdll!NtCreateWnfStateName` at `0x18001b03a`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionWNFAdHoc::Set(__int64 a1, const struct _GUID *a2, __int128 *a3)
{
  int v5; // eax
  unsigned int v7; // edi
  __int64 v8; // xmm1_8
  int AllAllowedSd; // eax
  TaskStore *v10; // rcx
  int v11; // ebp
  __int64 v12; // r8
  void *v13; // rbx
  struct _WNF_STATE_NAME *v14; // r14
  int WnfStateName; // eax
  __int64 *v16; // rdx
  __int128 v17; // [rsp+40h] [rbp-58h] BYREF
  __int64 v18; // [rsp+50h] [rbp-48h]
  void *Block[2]; // [rsp+58h] [rbp-40h] BYREF

  if ( !a2 || !a3 )
    return 0;
  v5 = *((_DWORD *)a3 + 2);
  if ( *((_QWORD *)a3 + 2) )
  {
    if ( !v5 )
      return 0;
  }
  else if ( v5 )
  {
    return 0;
  }
  v7 = 1;
  v8 = *((_QWORD *)a3 + 2);
  v17 = *a3;
  v18 = v8;
  if ( (byte_180030D08 & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(a1, GenerateAdhocState, 1);
  Block[0] = 0;
  AllAllowedSd = WnfCreateAllAllowedSd(Block);
  v11 = HRESULTFromNTSTATUS(AllAllowedSd);
  if ( v11 >= 0 )
  {
    v13 = Block[0];
    v14 = (struct _WNF_STATE_NAME *)(a1 + 160);
    WnfStateName = NtCreateWnfStateName(a1 + 160, 3, 0);
    v11 = HRESULTFromNTSTATUS(WnfStateName);
    free(v13);
    if ( v11 >= 0 )
    {
      *(struct _WNF_STATE_NAME *)&v17 = *v14;
      if ( !anonymous_namespace_::ActionWNF::Set(a1, (__int64)a2, (__int64)&v17)
        || (a2[2].Data4[4] & 1) == 0
        || !qword_180030AC8
        || (int)TaskStore::PersistAdhocStateName(v10, a2 + 1, *v14) >= 0
        || (byte_180030D08 & 0x20) == 0 )
      {
        goto LABEL_20;
      }
      v16 = ErrorPersistAdhocState;
      goto LABEL_19;
    }
    if ( (byte_180030D08 & 0x10) != 0 )
    {
      v16 = ErrorCreateAdhocState;
LABEL_19:
      McGenEventWrite_EventWriteTransfer(v10, v16, v12, 1, Block);
    }
  }
LABEL_20:
  if ( (byte_180030D03 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v10, PublishAdhocSet, v12, 1, Block);
  if ( v11 < 0 || !*(_QWORD *)(a1 + 176) )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x18001af50  mov     [rsp+arg_18], rbx
0x18001af55  push    rbp
0x18001af56  push    rsi
0x18001af57  push    rdi
0x18001af58  push    r14
0x18001af5a  push    r15
0x18001af5c  sub     rsp, 70h
0x18001af60  mov     rax, cs:__security_cookie
0x18001af67  xor     rax, rsp
0x18001af6a  mov     [rsp+98h+var_30], rax
0x18001af6f  mov     rsi, rdx
0x18001af72  mov     r15, rcx
0x18001af75  test    rdx, rdx
0x18001af78  jz      short loc_18001AF8E
0x18001af7a  test    r8, r8
0x18001af7d  jz      short loc_18001AF8E
0x18001af7f  cmp     qword ptr [r8+10h], 0
0x18001af84  mov     eax, [r8+8]
0x18001af88  jnz     short loc_18001AFB1
0x18001af8a  test    eax, eax
0x18001af8c  jz      short loc_18001AFB5
0x18001af8e  xor     eax, eax
0x18001af90  mov     rcx, [rsp+98h+var_30]
0x18001af95  xor     rcx, rsp; StackCookie
0x18001af98  call    __security_check_cookie
0x18001af9d  mov     rbx, [rsp+98h+arg_18]
0x18001afa5  add     rsp, 70h
0x18001afa9  pop     r15
0x18001afab  pop     r14
0x18001afad  pop     rdi
0x18001afae  pop     rsi
0x18001afaf  pop     rbp
0x18001afb0  retn
0x18001afb1  test    eax, eax
0x18001afb3  jz      short loc_18001AF8E
0x18001afb5  test    cs:byte_180030D08, 8
0x18001afbc  mov     edi, 1
0x18001afc1  movups  xmm0, xmmword ptr [r8]
0x18001afc5  movsd   xmm1, qword ptr [r8+10h]
0x18001afcb  movups  [rsp+98h+var_58], xmm0
0x18001afd0  movsd   [rsp+98h+var_48], xmm1
0x18001afd6  jz      short loc_18001AFE7
0x18001afd8  mov     r8d, edi
0x18001afdb  lea     rdx, GenerateAdhocState
0x18001afe2  call    McTemplateU0q_EventWriteTransfer
0x18001afe7  lea     rcx, [rsp+98h+Block]
0x18001afec  mov     [rsp+98h+Block], 0
0x18001aff5  call    WnfCreateAllAllowedSd
0x18001affa  mov     ecx, eax; int
0x18001affc  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x18001b001  mov     ebp, eax
0x18001b003  test    eax, eax
0x18001b005  js      loc_18001B0C6
0x18001b00b  mov     rbx, [rsp+98h+Block]
0x18001b010  lea     r14, [r15+0A0h]
0x18001b017  mov     eax, [r14+8]
0x18001b01b  xor     r9d, r9d
0x18001b01e  mov     [rsp+98h+var_68], rbx
0x18001b023  xor     r8d, r8d
0x18001b026  mov     [rsp+98h+var_70], eax
0x18001b02a  mov     rcx, r14
0x18001b02d  mov     [rsp+98h+var_78], 0
0x18001b036  lea     edx, [r9+3]
0x18001b03a  call    cs:__imp_NtCreateWnfStateName
0x18001b040  mov     ecx, eax; int
0x18001b042  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x18001b047  mov     rcx, rbx; Block
0x18001b04a  mov     ebp, eax
0x18001b04c  call    cs:__imp_free
0x18001b052  test    ebp, ebp
0x18001b054  js      short loc_18001B0A4
0x18001b056  mov     rax, [r14]
0x18001b059  lea     r8, [rsp+98h+var_58]
0x18001b05e  mov     rdx, rsi
0x18001b061  mov     qword ptr [rsp+98h+var_58], rax
0x18001b066  mov     rcx, r15
0x18001b069  call    _anonymous_namespace___ActionWNF__Set
0x18001b06e  test    eax, eax
0x18001b070  jz      short loc_18001B0C6
0x18001b072  test    [rsi+2Ch], dil
0x18001b076  jz      short loc_18001B0C6
0x18001b078  cmp     cs:qword_180030AC8, 0
0x18001b080  jz      short loc_18001B0C6
0x18001b082  mov     r8, [r14]; struct _WNF_STATE_NAME
0x18001b085  lea     rdx, [rsi+10h]; struct _GUID *
0x18001b089  call    ?PersistAdhocStateName@TaskStore@@QEAAJAEBU_GUID@@U_WNF_STATE_NAME@@@Z; TaskStore::PersistAdhocStateName(_GUID const &,_WNF_STATE_NAME)
0x18001b08e  test    eax, eax
0x18001b090  jns     short loc_18001B0C6
0x18001b092  test    cs:byte_180030D08, 20h
0x18001b099  jz      short loc_18001B0C6
0x18001b09b  lea     rdx, ErrorPersistAdhocState
0x18001b0a2  jmp     short loc_18001B0B4
0x18001b0a4  test    cs:byte_180030D08, 10h
0x18001b0ab  jz      short loc_18001B0C6
0x18001b0ad  lea     rdx, ErrorCreateAdhocState
0x18001b0b4  lea     rax, [rsp+98h+Block]
0x18001b0b9  mov     r9d, edi
0x18001b0bc  mov     [rsp+98h+var_78], rax
0x18001b0c1  call    McGenEventWrite_EventWriteTransfer
0x18001b0c6  test    cs:byte_180030D03, 4
0x18001b0cd  jz      short loc_18001B0E8
0x18001b0cf  lea     rax, [rsp+98h+Block]
0x18001b0d4  mov     r9d, edi
0x18001b0d7  lea     rdx, PublishAdhocSet
0x18001b0de  mov     [rsp+98h+var_78], rax
0x18001b0e3  call    McGenEventWrite_EventWriteTransfer
0x18001b0e8  test    ebp, ebp
0x18001b0ea  js      short loc_18001B0F6
0x18001b0ec  cmp     qword ptr [r15+0B0h], 0
0x18001b0f4  jnz     short loc_18001B0F8
0x18001b0f6  xor     edi, edi
0x18001b0f8  mov     eax, edi
0x18001b0fa  jmp     loc_18001AF90
```
