# Interrupter_ReleaseInterrupter

- ea: `0x14007d654`
- end: `0x14007d7d4`
- name: `Interrupter_ReleaseInterrupter`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14007d5cc`

## callees

- `0x1400054dc`
- `0x14001c040`
- `0x14001d118`
- `0x14007d654`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14007d786`
- `ntoskrnl!IoFreeWorkItem` at `0x14007d786`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14007d7b3`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x14007d7b3`

## pseudocode

```c
void __fastcall Interrupter_ReleaseInterrupter(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdi
  _DWORD *v5; // rdx
  __int64 v6; // r8
  _DWORD *v7; // rdx
  __int64 v8; // r8
  _DWORD *v9; // rdx
  _QWORD **v10; // rdi
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  struct _IO_WORKITEM *v13; // rcx
  __int64 v14; // rdx
  signed __int32 v15[18]; // [rsp+0h] [rbp-48h] BYREF

  if ( *(_DWORD *)(a1 + 116) == 1 )
  {
    v2 = *(_QWORD *)(a1 + 8);
    v3 = *(_QWORD *)(v2 + 120);
    if ( (*(_DWORD *)(v2 + 744) & 0x400LL) == 0 )
    {
      v4 = *(_QWORD *)(v2 + 88);
      v5 = (_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL);
      if ( *(_BYTE *)(v4 + 137) )
      {
        *v5 = 0;
        _InterlockedOr(v15, 0);
      }
      else
      {
        XilRegister_WriteUlong(v4, v5, 0);
      }
      v6 = *(_QWORD *)(a1 + 24);
      v7 = (_DWORD *)(v6 + 16);
      if ( *(_BYTE *)(v4 + 137) )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v4 + 8) + 736LL) & 1) != 0 )
        {
          *v7 = 0;
          _InterlockedOr(v15, 0);
          *(_DWORD *)(v6 + 20) = 0;
        }
        else
        {
          *(_QWORD *)v7 = 0;
        }
        _InterlockedOr(v15, 0);
      }
      else
      {
        XilRegister_WriteUlong64(v4, v7, 0);
      }
      v8 = *(_QWORD *)(a1 + 24);
      v9 = (_DWORD *)(v8 + 24);
      if ( *(_BYTE *)(v4 + 137) )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v4 + 8) + 736LL) & 1) != 0 )
        {
          *v9 = 0;
          _InterlockedOr(v15, 0);
          *(_DWORD *)(v8 + 28) = 0;
        }
        else
        {
          *(_QWORD *)v9 = 0;
        }
        _InterlockedOr(v15, 0);
      }
      else
      {
        XilRegister_WriteUlong64(v4, v9, 0);
      }
    }
    if ( *(_QWORD *)(a1 + 168) )
    {
      XilCommonBuffer_ReleaseBuffer(v3);
      *(_QWORD *)(a1 + 168) = 0;
    }
    v10 = (_QWORD **)(a1 + 176);
    while ( 1 )
    {
      v11 = *v10;
      if ( *v10 == v10 )
        break;
      if ( (_QWORD **)v11[1] != v10 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
        __fastfail(3u);
      *v10 = v12;
      v12[1] = v10;
      XilCommonBuffer_ReleaseBuffer(v3);
    }
    v13 = *(struct _IO_WORKITEM **)(a1 + 216);
    if ( v13 )
    {
      IoFreeWorkItem(v13);
      *(_QWORD *)(a1 + 216) = 0;
    }
    v14 = *(_QWORD *)(a1 + 16);
    if ( v14 && v14 != *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL) )
      imp_WppRecorderLogDelete(WPP_GLOBAL_Control, v14);
    *(_QWORD *)(a1 + 16) = 0;
  }
  *(_DWORD *)(a1 + 116) = 2;
}

```

## disassembly

```asm
0x14007d654  push    rbx
0x14007d656  push    rbp
0x14007d657  push    rsi
0x14007d658  push    rdi
0x14007d659  sub     rsp, 28h
0x14007d65d  cmp     dword ptr [rcx+74h], 1
0x14007d661  mov     rbx, rcx
0x14007d664  jnz     loc_14007D7C3
0x14007d66a  mov     rdi, [rcx+8]
0x14007d66e  xor     ebp, ebp
0x14007d670  mov     eax, [rdi+2E8h]
0x14007d676  mov     rsi, [rdi+78h]
0x14007d67a  bt      rax, 0Ah
0x14007d67f  jb      loc_14007D729
0x14007d685  mov     rdi, [rdi+58h]
0x14007d689  mov     rdx, [rcx+18h]
0x14007d68d  add     rdx, 8
0x14007d691  cmp     [rdi+89h], bpl
0x14007d698  jz      short loc_14007D6A2
0x14007d69a  mov     [rdx], ebp
0x14007d69c  lock or [rsp+48h+var_48], ebp
0x14007d6a0  jmp     short loc_14007D6AD
0x14007d6a2  xor     r8d, r8d
0x14007d6a5  mov     rcx, rdi
0x14007d6a8  call    XilRegister_WriteUlong
0x14007d6ad  mov     r8, [rbx+18h]
0x14007d6b1  lea     rdx, [r8+10h]
0x14007d6b5  cmp     [rdi+89h], bpl
0x14007d6bc  jz      short loc_14007D6E0
0x14007d6be  mov     rax, [rdi+8]
0x14007d6c2  test    byte ptr [rax+2E0h], 1
0x14007d6c9  jnz     short loc_14007D6D0
0x14007d6cb  mov     [rdx], rbp
0x14007d6ce  jmp     short loc_14007D6DA
0x14007d6d0  mov     [rdx], ebp
0x14007d6d2  lock or [rsp+48h+var_48], ebp
0x14007d6d6  mov     [r8+14h], ebp
0x14007d6da  lock or [rsp+48h+var_48], ebp
0x14007d6de  jmp     short loc_14007D6EB
0x14007d6e0  xor     r8d, r8d
0x14007d6e3  mov     rcx, rdi
0x14007d6e6  call    XilRegister_WriteUlong64
0x14007d6eb  mov     r8, [rbx+18h]
0x14007d6ef  lea     rdx, [r8+18h]
0x14007d6f3  cmp     [rdi+89h], bpl
0x14007d6fa  jz      short loc_14007D71E
0x14007d6fc  mov     rax, [rdi+8]
0x14007d700  test    byte ptr [rax+2E0h], 1
0x14007d707  jnz     short loc_14007D70E
0x14007d709  mov     [rdx], rbp
0x14007d70c  jmp     short loc_14007D718
0x14007d70e  mov     [rdx], ebp
0x14007d710  lock or [rsp+48h+var_48], ebp
0x14007d714  mov     [r8+1Ch], ebp
0x14007d718  lock or [rsp+48h+var_48], ebp
0x14007d71c  jmp     short loc_14007D729
0x14007d71e  xor     r8d, r8d
0x14007d721  mov     rcx, rdi
0x14007d724  call    XilRegister_WriteUlong64
0x14007d729  mov     rdx, [rbx+0A8h]
0x14007d730  test    rdx, rdx
0x14007d733  jz      short loc_14007D744
0x14007d735  mov     rcx, rsi
0x14007d738  call    XilCommonBuffer_ReleaseBuffer
0x14007d73d  mov     [rbx+0A8h], rbp
0x14007d744  lea     rdi, [rbx+0B0h]
0x14007d74b  mov     rdx, [rdi]
0x14007d74e  cmp     rdx, rdi
0x14007d751  jz      short loc_14007D77A
0x14007d753  cmp     [rdx+8], rdi
0x14007d757  jnz     short loc_14007D773
0x14007d759  mov     rax, [rdx]
0x14007d75c  cmp     [rax+8], rdx
0x14007d760  jnz     short loc_14007D773
0x14007d762  mov     [rdi], rax
0x14007d765  mov     rcx, rsi
0x14007d768  mov     [rax+8], rdi
0x14007d76c  call    XilCommonBuffer_ReleaseBuffer
0x14007d771  jmp     short loc_14007D74B
0x14007d773  mov     ecx, 3
0x14007d778  int     29h; Win8: RtlFailFast(ecx)
0x14007d77a  mov     rcx, [rbx+0D8h]; IoWorkItem
0x14007d781  test    rcx, rcx
0x14007d784  jz      short loc_14007D799
0x14007d786  call    cs:__imp_IoFreeWorkItem
0x14007d78d  nop     dword ptr [rax+rax+00h]
0x14007d792  mov     [rbx+0D8h], rbp
0x14007d799  mov     rdx, [rbx+10h]
0x14007d79d  test    rdx, rdx
0x14007d7a0  jz      short loc_14007D7BF
0x14007d7a2  mov     rax, [rbx+8]
0x14007d7a6  cmp     rdx, [rax+48h]
0x14007d7aa  jz      short loc_14007D7BF
0x14007d7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d7b3  call    cs:__imp_imp_WppRecorderLogDelete
0x14007d7ba  nop     dword ptr [rax+rax+00h]
0x14007d7bf  mov     [rbx+10h], rbp
0x14007d7c3  mov     dword ptr [rbx+74h], 2
0x14007d7ca  add     rsp, 28h
0x14007d7ce  pop     rdi
0x14007d7cf  pop     rsi
0x14007d7d0  pop     rbp
0x14007d7d1  pop     rbx
0x14007d7d2  retn
```
