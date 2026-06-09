# CCategoryInfoLog::WriteCategories(void)

- ea: `0x18000c2cc`
- end: `0x18000c3b5`
- name: `?WriteCategories@CCategoryInfoLog@@AEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(CCategoryInfoLog *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c3bc`

## callees

- `0x18000c2cc`
- `0x18001b1a0`
- `0x18002a970`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CCategoryInfoLog::WriteCategories(CCategoryInfoLog *this)
{
  unsigned int v2; // esi
  __int64 v3; // rax
  unsigned int v4; // ebp
  __int64 v5; // rbx
  __int64 v6; // rax
  void **v8; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+30h] [rbp-38h]
  __int64 v11; // [rsp+38h] [rbp-30h]

  v2 = 0;
  v3 = *((_QWORD *)this + 10);
  if ( *(_DWORD *)v3 )
  {
    v4 = 0;
    do
    {
      v5 = 32LL * v4;
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xC27u, *(_QWORD *)(*(_QWORD *)(v3 + 8) + v5 + 8));
      v6 = v5 + *(_QWORD *)(*((_QWORD *)this + 10) + 8LL);
      v9 = 0;
      v10 = 1;
      v8 = &CCategoryInfo::`vftable';
      v11 = v6;
      if ( (int)CGroupPolicyLog::WriteNewRecord(this, (struct CGroupPolicyRecord *)&v8) < 0 )
      {
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC28u, *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL) + 8LL), v2);
        v2 = 1;
      }
      v8 = &CGroupPolicyRecord::`vftable';
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      ++v4;
      v3 = *((_QWORD *)this + 10);
    }
    while ( v4 < *(_DWORD *)v3 );
  }
  return v2;
}

```

## disassembly

```asm
0x18000c2cc  push    rbx
0x18000c2ce  push    rbp
0x18000c2cf  push    rsi
0x18000c2d0  push    rdi
0x18000c2d1  sub     rsp, 48h
0x18000c2d5  mov     rdi, rcx
0x18000c2d8  xor     esi, esi
0x18000c2da  mov     rax, [rcx+50h]
0x18000c2de  cmp     [rax], esi
0x18000c2e0  jbe     loc_18000C3AA
0x18000c2e6  xor     ebp, ebp
0x18000c2e8  mov     ebx, ebp
0x18000c2ea  shl     rbx, 5
0x18000c2ee  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c2f5  jz      short loc_18000C30F
0x18000c2f7  mov     r8, [rax+8]
0x18000c2fb  mov     r8, [r8+rbx+8]
0x18000c300  mov     edx, 0C27h; unsigned int
0x18000c305  mov     ecx, 4; unsigned int
0x18000c30a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c30f  mov     rax, [rdi+50h]
0x18000c313  mov     rax, [rax+8]
0x18000c317  add     rax, rbx
0x18000c31a  mov     [rsp+68h+var_40], 0
0x18000c323  mov     [rsp+68h+var_38], 1
0x18000c32b  lea     rcx, ??_7CCategoryInfo@@6B@; const CCategoryInfo::`vftable'
0x18000c332  mov     [rsp+68h+var_48], rcx
0x18000c337  mov     [rsp+68h+var_30], rax
0x18000c33c  lea     rdx, [rsp+68h+var_48]; struct CGroupPolicyRecord *
0x18000c341  mov     rcx, rdi; this
0x18000c344  call    ?WriteNewRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@@Z; CGroupPolicyLog::WriteNewRecord(CGroupPolicyRecord *)
0x18000c349  test    eax, eax
0x18000c34b  jns     short loc_18000C379
0x18000c34d  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c354  jz      short loc_18000C374
0x18000c356  mov     rax, [rdi+50h]
0x18000c35a  mov     r8, [rax+8]
0x18000c35e  mov     r9d, esi
0x18000c361  mov     r8, [r8+8]
0x18000c365  mov     edx, 0C28h; unsigned int
0x18000c36a  mov     ecx, 4; unsigned int
0x18000c36f  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c374  mov     esi, 1
0x18000c379  lea     rax, ??_7CGroupPolicyRecord@@6B@; const CGroupPolicyRecord::`vftable'
0x18000c380  mov     [rsp+68h+var_48], rax
0x18000c385  mov     rcx, [rsp+68h+var_40]
0x18000c38a  test    rcx, rcx
0x18000c38d  jz      short loc_18000C39C
0x18000c38f  mov     rax, [rcx]
0x18000c392  mov     rax, [rax+10h]
0x18000c396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c39b  nop
0x18000c39c  inc     ebp
0x18000c39e  mov     rax, [rdi+50h]
0x18000c3a2  cmp     ebp, [rax]
0x18000c3a4  jb      loc_18000C2E8
0x18000c3aa  mov     eax, esi
0x18000c3ac  add     rsp, 48h
0x18000c3b0  pop     rdi
0x18000c3b1  pop     rsi
0x18000c3b2  pop     rbp
0x18000c3b3  pop     rbx
0x18000c3b4  retn
```
