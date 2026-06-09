# CfGetSyncRootInfoByPath

- ea: `0x18000f610`
- end: `0x18000f6f4`
- name: `CfGetSyncRootInfoByPath`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800022ee`
- `0x18000f610`
- `0x18000f7c4`
- `0x180011e18`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000f654`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000f654`

## string_xrefs

- `0x18000f67f`: `CfpGetSyncRootInfoByPath Failed`

## pseudocode

```c
__int64 __fastcall CfGetSyncRootInfoByPath(__int64 a1, int a2, const WCHAR *a3, int a4, __int64 a5)
{
  const WCHAR *v6; // rsi
  const WCHAR *v10; // rbp
  int SyncRootInfoByPath; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rcx
  unsigned __int64 UnbiasedTime; // [rsp+40h] [rbp-A8h] BYREF
  int v16; // [rsp+50h] [rbp-98h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp-90h]

  UnbiasedTime = 0;
  v6 = &SourceString;
  v10 = &SourceString;
  memset_0(&v16, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  SyncRootInfoByPath = CfpGetSyncRootInfoByPath(a1, a2, (_DWORD)a3, a4, a5);
  v12 = SyncRootInfoByPath;
  if ( SyncRootInfoByPath > -1 )
  {
    v13 = 0;
    if ( a2 == 1 )
    {
      v6 = a3 + 14;
      v10 = a3 + 270;
    }
    else if ( a2 == 2 )
    {
      v6 = a3 + 2;
      v10 = a3 + 258;
    }
  }
  else
  {
    v13 = L"CfpGetSyncRootInfoByPath Failed";
  }
  v17 = v13;
  TlmLogApiReliability(0x18u, 0, a1, v6, v10, UnbiasedTime, &v16, SyncRootInfoByPath);
  return v12;
}

```

## disassembly

```asm
0x18000f610  push    rbx
0x18000f612  push    rbp
0x18000f613  push    rsi
0x18000f614  push    rdi
0x18000f615  push    r14
0x18000f617  push    r15
0x18000f619  sub     rsp, 0B8h
0x18000f620  mov     r14d, edx
0x18000f623  mov     [rsp+0E8h+UnbiasedTime], 0
0x18000f62c  xor     edx, edx; Val
0x18000f62e  lea     rsi, SourceString
0x18000f635  mov     rdi, r8
0x18000f638  mov     r15, rcx
0x18000f63b  lea     rcx, [rsp+0E8h+var_98]; void *
0x18000f640  mov     ebx, r9d
0x18000f643  mov     rbp, rsi
0x18000f646  lea     r8d, [rdx+58h]; Size
0x18000f64a  call    memset_0
0x18000f64f  lea     rcx, [rsp+0E8h+UnbiasedTime]; UnbiasedTime
0x18000f654  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000f65a  mov     rax, [rsp+0E8h+arg_20]
0x18000f662  mov     r9d, ebx
0x18000f665  mov     r8, rdi
0x18000f668  mov     [rsp+0E8h+var_C8], rax
0x18000f66d  mov     edx, r14d
0x18000f670  mov     rcx, r15
0x18000f673  call    CfpGetSyncRootInfoByPath
0x18000f678  mov     ebx, eax
0x18000f67a  cmp     eax, 0FFFFFFFFh
0x18000f67d  jg      short loc_18000F688
0x18000f67f  lea     rcx, aCfpgetsyncroot_0; "CfpGetSyncRootInfoByPath Failed"
0x18000f686  jmp     short loc_18000F6AE
0x18000f688  xor     ecx, ecx
0x18000f68a  cmp     r14d, 1
0x18000f68e  jnz     short loc_18000F69D
0x18000f690  lea     rsi, [rdi+1Ch]
0x18000f694  lea     rbp, [rdi+21Ch]
0x18000f69b  jmp     short loc_18000F6AE
0x18000f69d  cmp     r14d, 2
0x18000f6a1  jnz     short loc_18000F6AE
0x18000f6a3  lea     rsi, [rdi+4]
0x18000f6a7  lea     rbp, [rdi+204h]
0x18000f6ae  mov     [rsp+0E8h+var_B0], ebx
0x18000f6b2  lea     rax, [rsp+0E8h+var_98]
0x18000f6b7  mov     [rsp+0E8h+var_B8], rax
0x18000f6bc  mov     r9, rsi
0x18000f6bf  mov     rax, [rsp+0E8h+UnbiasedTime]
0x18000f6c4  mov     r8, r15
0x18000f6c7  mov     [rsp+0E8h+var_90], rcx
0x18000f6cc  xor     edx, edx
0x18000f6ce  mov     [rsp+0E8h+var_C0], rax
0x18000f6d3  mov     ecx, 18h
0x18000f6d8  mov     [rsp+0E8h+var_C8], rbp
0x18000f6dd  call    TlmLogApiReliability
0x18000f6e2  mov     eax, ebx
0x18000f6e4  add     rsp, 0B8h
0x18000f6eb  pop     r15
0x18000f6ed  pop     r14
0x18000f6ef  pop     rdi
0x18000f6f0  pop     rsi
0x18000f6f1  pop     rbp
0x18000f6f2  pop     rbx
0x18000f6f3  retn
```
