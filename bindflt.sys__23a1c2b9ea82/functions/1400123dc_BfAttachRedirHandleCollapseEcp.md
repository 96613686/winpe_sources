# BfAttachRedirHandleCollapseEcp

- ea: `0x1400123dc`
- end: `0x1400124fe`
- name: `BfAttachRedirHandleCollapseEcp`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011eb0`

## callees

- `0x1400123dc`

## import_xrefs

- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400124ad`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400124ad`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14001246c`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14001246c`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x1400124c8`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x1400124c8`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140012423`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140012423`

## pseudocode

```c
__int64 __fastcall BfAttachRedirHandleCollapseEcp(__int64 a1, struct _ECP_LIST *a2, _BYTE *a3)
{
  struct _FLT_FILTER *v5; // rcx
  NTSTATUS ExtraCreateParameter; // eax
  NTSTATUS Parameter; // ebx
  char *v9; // rax
  ULONG v11; // [rsp+60h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  EcpContext = 0;
  v5 = *(struct _FLT_FILTER **)(a1 + 8);
  v11 = 0;
  ExtraCreateParameter = FltFindExtraCreateParameter(v5, a2, &GUID_ECP_NETWORK_OPEN_CONTEXT, &EcpContext, &v11);
  Parameter = ExtraCreateParameter;
  if ( ExtraCreateParameter != -1073741275 )
  {
    if ( ExtraCreateParameter < 0 )
      return (unsigned int)Parameter;
    goto LABEL_7;
  }
  Parameter = FltAllocateExtraCreateParameter(
                *(PFLT_FILTER *)(a1 + 8),
                &GUID_ECP_NETWORK_OPEN_CONTEXT,
                0x1Cu,
                0,
                0,
                0x68634642u,
                &EcpContext);
  if ( Parameter >= 0 )
  {
    v9 = (char *)EcpContext;
    *(_OWORD *)EcpContext = 0;
    *(_OWORD *)(v9 + 12) = 0;
    *(_WORD *)EcpContext = 28;
    *((_WORD *)EcpContext + 1) = 0;
    Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)(a1 + 8), a2, EcpContext);
    if ( Parameter < 0 )
    {
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)(a1 + 8), EcpContext);
      return (unsigned int)Parameter;
    }
    *a3 = 1;
LABEL_7:
    *((_DWORD *)EcpContext + 3) |= 1u;
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x1400123dc  mov     r11, rsp
0x1400123df  mov     [r11+10h], rbx
0x1400123e3  mov     [r11+20h], rbp
0x1400123e7  push    rsi
0x1400123e8  push    rdi
0x1400123e9  push    r15
0x1400123eb  sub     rsp, 40h
0x1400123ef  mov     rsi, r8
0x1400123f2  mov     byte ptr [r8], 0
0x1400123f6  mov     rdi, rcx
0x1400123f9  mov     qword ptr [r11+18h], 0
0x140012401  mov     rcx, [rcx+8]; Filter
0x140012405  lea     rax, [r11+8]
0x140012409  lea     r8, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x140012410  mov     [r11-38h], rax
0x140012414  lea     r9, [r11+18h]; EcpContext
0x140012418  mov     [rsp+58h+arg_0], 0
0x140012420  mov     rbp, rdx
0x140012423  call    cs:__imp_FltFindExtraCreateParameter
0x14001242a  nop     dword ptr [rax+rax+00h]
0x14001242f  mov     ebx, eax
0x140012431  cmp     eax, 0C0000225h
0x140012436  jnz     loc_1400124DB
0x14001243c  mov     rcx, [rdi+8]; Filter
0x140012440  lea     rax, [rsp+58h+arg_10]
0x140012445  mov     [rsp+58h+EcpContext], rax; EcpContext
0x14001244a  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x140012451  xor     r9d, r9d; Flags
0x140012454  mov     [rsp+58h+PoolTag], 68634642h; PoolTag
0x14001245c  mov     [rsp+58h+CleanupCallback], 0; CleanupCallback
0x140012465  lea     r15d, [r9+1Ch]
0x140012469  mov     r8d, r15d; SizeOfContext
0x14001246c  call    cs:__imp_FltAllocateExtraCreateParameter
0x140012473  nop     dword ptr [rax+rax+00h]
0x140012478  mov     ebx, eax
0x14001247a  test    eax, eax
0x14001247c  js      short loc_1400124E8
0x14001247e  mov     rax, [rsp+58h+arg_10]
0x140012483  xorps   xmm0, xmm0
0x140012486  xor     ecx, ecx
0x140012488  mov     rdx, rbp; EcpList
0x14001248b  movups  xmmword ptr [rax], xmm0
0x14001248e  movups  xmmword ptr [rax+0Ch], xmm0
0x140012492  mov     rax, [rsp+58h+arg_10]
0x140012497  mov     [rax], r15w
0x14001249b  mov     rax, [rsp+58h+arg_10]
0x1400124a0  mov     [rax+2], cx
0x1400124a4  mov     r8, [rsp+58h+arg_10]; EcpContext
0x1400124a9  mov     rcx, [rdi+8]; Filter
0x1400124ad  call    cs:__imp_FltInsertExtraCreateParameter
0x1400124b4  nop     dword ptr [rax+rax+00h]
0x1400124b9  mov     ebx, eax
0x1400124bb  test    eax, eax
0x1400124bd  jns     short loc_1400124D6
0x1400124bf  mov     rdx, [rsp+58h+arg_10]; EcpContext
0x1400124c4  mov     rcx, [rdi+8]; Filter
0x1400124c8  call    cs:__imp_FltFreeExtraCreateParameter
0x1400124cf  nop     dword ptr [rax+rax+00h]
0x1400124d4  jmp     short loc_1400124E8
0x1400124d6  mov     byte ptr [rsi], 1
0x1400124d9  jmp     short loc_1400124DF
0x1400124db  test    eax, eax
0x1400124dd  js      short loc_1400124E8
0x1400124df  mov     rax, [rsp+58h+arg_10]
0x1400124e4  or      dword ptr [rax+0Ch], 1
0x1400124e8  mov     rbp, [rsp+58h+arg_18]
0x1400124ed  mov     eax, ebx
0x1400124ef  mov     rbx, [rsp+58h+arg_8]
0x1400124f4  add     rsp, 40h
0x1400124f8  pop     r15
0x1400124fa  pop     rdi
0x1400124fb  pop     rsi
0x1400124fc  retn
```
