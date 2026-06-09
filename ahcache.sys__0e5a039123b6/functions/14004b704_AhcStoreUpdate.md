# AhcStoreUpdate

- ea: `0x14004b704`
- end: `0x14004b7de`
- name: `AhcStoreUpdate`
- size: `218`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, _OWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x14004b4ac`

## callees

- `0x140007ad0`
- `0x1400276d0`
- `0x14003e364`
- `0x14004b704`
- `0x14004b7e4`
- `0x14004bc98`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14004b733`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14004b733`

## string_xrefs

- `0x14004b778`: `Failed to copy item [%x]`
- `0x14004b79f`: `AhcStoreUpdate`

## pseudocode

```c
__int64 __fastcall AhcStoreUpdate(PRTL_AVL_TABLE Table, _OWORD *a2, __int64 a3)
{
  _QWORD *v6; // rbp
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // r8
  const char *v10; // r9
  _OWORD v12[5]; // [rsp+30h] [rbp-58h] BYREF

  memset(v12, 0, 48);
  *(_OWORD *)((char *)&v12[1] + 8) = *a2;
  v6 = RtlLookupElementGenericTableAvl(Table, v12);
  if ( v6 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))&Table[1].DepthOfTree)(v6[5], a3);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v8 = AhcStorePromote(Table, a2);
      v7 = v8;
      if ( v8 >= 0 )
      {
        ++*(_DWORD *)(*(_QWORD *)&Table[1].BalancedRoot.Balance + 16LL);
        return 0;
      }
      v9 = 1052;
      v10 = "Failed to promote a store entry [%x]";
    }
    else
    {
      v9 = 1041;
      v10 = "Failed to copy item [%x]";
    }
    AslLogCallPrintf(1, "AhcStoreUpdate", v9, v10, v8);
    AhcpStoreEntryRemove(Table, v6);
  }
  else
  {
    return (unsigned int)AhcStoreInsert(Table);
  }
  return v7;
}

```

## disassembly

```asm
0x14004b704  mov     rax, rsp
0x14004b707  push    rbx
0x14004b708  push    rbp
0x14004b709  push    rsi
0x14004b70a  push    rdi
0x14004b70b  sub     rsp, 68h
0x14004b70f  xorps   xmm0, xmm0
0x14004b712  mov     rsi, rdx
0x14004b715  movups  xmmword ptr [rax-48h], xmm0
0x14004b719  mov     rbx, r8
0x14004b71c  mov     rdi, rcx
0x14004b71f  movups  xmmword ptr [rax-38h], xmm0
0x14004b723  movups  xmmword ptr [rax-58h], xmm0
0x14004b727  movups  xmm0, xmmword ptr [rdx]
0x14004b72a  lea     rdx, [rax-58h]; Buffer
0x14004b72e  movdqu  xmmword ptr [rax-40h], xmm0
0x14004b733  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14004b73a  nop     dword ptr [rax+rax+00h]
0x14004b73f  mov     rbp, rax
0x14004b742  test    rax, rax
0x14004b745  jnz     short loc_14004B759
0x14004b747  mov     r8, rbx
0x14004b74a  mov     rdx, rsi
0x14004b74d  mov     rcx, rdi; Table
0x14004b750  call    AhcStoreInsert
0x14004b755  mov     ebx, eax
0x14004b757  jmp     short loc_14004B7D2
0x14004b759  mov     rax, [rdi+98h]
0x14004b760  mov     rdx, rbx
0x14004b763  mov     rcx, [rbp+28h]
0x14004b767  call    _guard_dispatch_icall
0x14004b76c  mov     ebx, eax
0x14004b76e  test    eax, eax
0x14004b770  jns     short loc_14004B781
0x14004b772  mov     r8d, 411h
0x14004b778  lea     r9, aFailedToCopyIt; "Failed to copy item [%x]"
0x14004b77f  jmp     short loc_14004B79F
0x14004b781  mov     rdx, rsi
0x14004b784  mov     rcx, rdi
0x14004b787  call    AhcStorePromote
0x14004b78c  mov     ebx, eax
0x14004b78e  test    eax, eax
0x14004b790  jns     short loc_14004B7C1
0x14004b792  mov     r8d, 41Ch
0x14004b798  lea     r9, aFailedToPromot; "Failed to promote a store entry [%x]"
0x14004b79f  lea     rdx, aAhcstoreupdate; "AhcStoreUpdate"
0x14004b7a6  mov     [rsp+88h+var_68], eax
0x14004b7aa  mov     ecx, 1
0x14004b7af  call    AslLogCallPrintf
0x14004b7b4  mov     rdx, rbp
0x14004b7b7  mov     rcx, rdi
0x14004b7ba  call    AhcpStoreEntryRemove
0x14004b7bf  jmp     short loc_14004B7D2
0x14004b7c1  mov     rax, [rdi+80h]
0x14004b7c8  mov     ecx, 1
0x14004b7cd  add     [rax+10h], ecx
0x14004b7d0  xor     ebx, ebx
0x14004b7d2  mov     eax, ebx
0x14004b7d4  add     rsp, 68h
0x14004b7d8  pop     rdi
0x14004b7d9  pop     rsi
0x14004b7da  pop     rbp
0x14004b7db  pop     rbx
0x14004b7dc  retn
```
