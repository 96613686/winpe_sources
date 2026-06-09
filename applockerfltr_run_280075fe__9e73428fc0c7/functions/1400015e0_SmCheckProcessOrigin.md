# SmCheckProcessOrigin

- ea: `0x1400015e0`
- end: `0x14000166d`
- name: `SmCheckProcessOrigin`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007030`
- `0x140007410`

## callees

- `0x1400015e0`

## import_xrefs

- `FLTMGR!FltAcquireResourceShared` at `0x14000160d`
- `FLTMGR!FltAcquireResourceShared` at `0x14000160d`
- `FLTMGR!FltReleaseResource` at `0x140001652`
- `FLTMGR!FltReleaseResource` at `0x140001652`

## pseudocode

```c
__int64 __fastcall SmCheckProcessOrigin(__int64 a1)
{
  __int64 v1; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx

  v1 = 0;
  if ( qword_1400040D0 && _InterlockedCompareExchange64((volatile signed __int64 *)qword_1400040D0, 0, 0) )
  {
    FltAcquireResourceShared(Resource);
    if ( qword_1400040D0 )
    {
      v3 = *(_QWORD **)qword_1400040D0;
      if ( *(_QWORD *)qword_1400040D0 )
      {
        v4 = (_QWORD *)v3[2];
        while ( a1 != v4[2] )
        {
          v4 = (_QWORD *)*v4;
          if ( v4 == v3 + 2 )
            goto LABEL_9;
        }
        v1 = *v3;
        _InterlockedIncrement((volatile signed __int32 *)(*v3 + 24LL));
      }
    }
LABEL_9:
    FltReleaseResource(Resource);
  }
  return v1;
}

```

## disassembly

```asm
0x1400015e0  mov     [rsp+arg_0], rbx
0x1400015e5  push    rdi
0x1400015e6  sub     rsp, 20h
0x1400015ea  mov     r8, cs:qword_1400040D0
0x1400015f1  xor     ebx, ebx
0x1400015f3  mov     rdi, rcx
0x1400015f6  test    r8, r8
0x1400015f9  jz      short loc_14000165E
0x1400015fb  xor     edx, edx
0x1400015fd  xor     eax, eax
0x1400015ff  lock cmpxchg [r8], rdx
0x140001604  jz      short loc_14000165E
0x140001606  mov     rcx, cs:Resource; Resource
0x14000160d  call    cs:__imp_FltAcquireResourceShared
0x140001614  nop     dword ptr [rax+rax+00h]
0x140001619  mov     rax, cs:qword_1400040D0
0x140001620  test    rax, rax
0x140001623  jz      short loc_14000164B
0x140001625  mov     rax, [rax]
0x140001628  test    rax, rax
0x14000162b  jz      short loc_14000164B
0x14000162d  lea     rdx, [rax+10h]
0x140001631  mov     rcx, [rdx]
0x140001634  jmp     short loc_14000163E
0x140001636  mov     rcx, [rcx]
0x140001639  cmp     rcx, rdx
0x14000163c  jz      short loc_14000164B
0x14000163e  cmp     rdi, [rcx+10h]
0x140001642  jnz     short loc_140001636
0x140001644  mov     rbx, [rax]
0x140001647  lock inc dword ptr [rbx+18h]
0x14000164b  mov     rcx, cs:Resource; Resource
0x140001652  call    cs:__imp_FltReleaseResource
0x140001659  nop     dword ptr [rax+rax+00h]
0x14000165e  mov     rax, rbx
0x140001661  mov     rbx, [rsp+28h+arg_0]
0x140001666  add     rsp, 20h
0x14000166a  pop     rdi
0x14000166b  retn
```
