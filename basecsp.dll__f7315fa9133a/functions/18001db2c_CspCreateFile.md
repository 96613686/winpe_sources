# CspCreateFile

- ea: `0x18001db2c`
- end: `0x18001dbe5`
- name: `CspCreateFile`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180012fa0`
- `0x180020e28`

## callees

- `0x180017bac`
- `0x18001db2c`
- `0x18001f3a4`
- `0x180021b48`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall CspCreateFile(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rax
  int v10; // r9d

  v8 = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
  if ( !v8 )
  {
    v9 = *(_QWORD *)(a1 + 8);
    if ( v9 )
    {
      return (*(unsigned int (__fastcall **)(_QWORD, const char *, __int64, _QWORD, int))(v9 + 240))(
               *(_QWORD *)(a1 + 8),
               "mscp",
               a3,
               a4,
               1);
    }
    else
    {
      v8 = 87;
      WppTraceIndent(v7, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          v10,
          (__int64)"pCardState->pCardData");
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001db2c  mov     [rsp+arg_8], rdx
0x18001db31  push    rbx
0x18001db32  push    rbp
0x18001db33  push    rsi
0x18001db34  push    rdi
0x18001db35  sub     rsp, 38h
0x18001db39  xor     eax, eax
0x18001db3b  mov     rbp, r8
0x18001db3e  lea     r8, [rsp+58h+arg_8]
0x18001db43  mov     dword ptr [rsp+58h+arg_8], eax
0x18001db47  mov     esi, r9d
0x18001db4a  mov     word ptr [rsp+58h+arg_8+4], ax
0x18001db4f  mov     rdi, rcx
0x18001db52  lea     edx, [rax+4]
0x18001db55  call    CspIncrementCacheFreshness
0x18001db5a  mov     ebx, eax
0x18001db5c  test    eax, eax
0x18001db5e  jnz     short loc_18001DBDA
0x18001db60  mov     rax, [rdi+8]
0x18001db64  test    rax, rax
0x18001db67  jnz     short loc_18001DBB4
0x18001db69  lea     edx, [rax+2]
0x18001db6c  lea     ebx, [rax+57h]
0x18001db6f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001db74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db7b  lea     rax, WPP_GLOBAL_Control
0x18001db82  cmp     rcx, rax
0x18001db85  jz      short loc_18001DBDA
0x18001db87  test    byte ptr [rcx+1Ch], 1
0x18001db8b  jz      short loc_18001DBDA
0x18001db8d  cmp     byte ptr [rcx+19h], 2
0x18001db91  jb      short loc_18001DBDA
0x18001db93  mov     rcx, [rcx+10h]
0x18001db97  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001db9e  lea     edx, [rbx-3Dh]
0x18001dba1  mov     [rsp+58h+var_38], rax
0x18001dba6  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001dbad  call    WPP_SF_ss
0x18001dbb2  jmp     short loc_18001DBDA
0x18001dbb4  mov     rcx, rax
0x18001dbb7  mov     dword ptr [rsp+58h+var_38], 1
0x18001dbbf  mov     rax, [rax+0F0h]
0x18001dbc6  lea     rdx, aMscp; "mscp"
0x18001dbcd  mov     r9d, esi
0x18001dbd0  mov     r8, rbp
0x18001dbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbd8  mov     ebx, eax
0x18001dbda  mov     eax, ebx
0x18001dbdc  add     rsp, 38h
0x18001dbe0  pop     rdi
0x18001dbe1  pop     rsi
0x18001dbe2  pop     rbp
0x18001dbe3  pop     rbx
0x18001dbe4  retn
```
