# CDevNotify::ProgressCallback(DDO_PROGRESS_REPORT const &)

- ea: `0x180028070`
- end: `0x1800281f8`
- name: `?ProgressCallback@CDevNotify@@QEAAXAEBUDDO_PROGRESS_REPORT@@@Z`
- size: `392`
- prototype: `void __fastcall(CDevNotify *__hidden this, const struct DDO_PROGRESS_REPORT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009640`

## callees

- `0x180021790`
- `0x180022070`
- `0x180028070`
- `0x180028588`
- `0x180028984`
- `0x1800289c4`
- `0x180028a18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800281a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800281a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028082`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028082`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800281be`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800281be`

## pseudocode

```c
void __fastcall CDevNotify::ProgressCallback(CDevNotify *this, const struct DDO_PROGRESS_REPORT *a2)
{
  struct _RPC_ASYNC_STATE *v4; // rsi
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // rdx
  PVOID *v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // [rsp+20h] [rbp-38h]
  int v13; // [rsp+28h] [rbp-30h]
  int Reply; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this);
  if ( !*(_DWORD *)a2 )
  {
    v9 = *((_DWORD *)a2 + 1);
    *((_DWORD *)this + 14) = v9;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_15;
    v10 = 19;
LABEL_13:
    v12 = v9;
    WPP_SF_id(v8[2], v10, v5, this);
    goto LABEL_14;
  }
  if ( *(_DWORD *)a2 == 1 )
  {
    v9 = *((_DWORD *)a2 + 1);
    *((_DWORD *)this + 13) = v9;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_15;
    v10 = 17;
    goto LABEL_13;
  }
  if ( *(_DWORD *)a2 != 2 )
  {
LABEL_14:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  v6 = *((_DWORD *)a2 + 1);
  *((_DWORD *)this + 11) = v6;
  v7 = *((unsigned int *)a2 + 2);
  *((_DWORD *)this + 12) = v7;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v13 = v7;
    v12 = v6;
    WPP_SF_idD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v5, this);
    goto LABEL_14;
  }
LABEL_15:
  if ( *((_QWORD *)this + 2) )
  {
    if ( (int)CDevNotify::_SupplyNotification(this, *((struct __MIDL_DsmRpcNotify_0002 **)this + 1)) >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_i(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids,
          *((_QWORD *)this + 2),
          v12,
          v13);
      v4 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = 0;
      *((_QWORD *)this + 1) = 0;
    }
  }
  else if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
  {
    WPP_SF_(v8[2], 21, &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this);
  if ( v4 )
  {
    Reply = 0;
    v11 = RpcAsyncCompleteCall(v4, &Reply);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids, v11);
    }
  }
}

```

## disassembly

```asm
0x180028070  push    rbx
0x180028072  push    rsi
0x180028073  push    rdi
0x180028074  push    r15
0x180028076  sub     rsp, 38h
0x18002807a  mov     rdi, rdx
0x18002807d  mov     rbx, rcx
0x180028080  xor     esi, esi
0x180028082  call    cs:__imp_AcquireSRWLockExclusive
0x180028088  mov     ecx, [rdi]
0x18002808a  lea     r15, WPP_GLOBAL_Control
0x180028091  test    ecx, ecx
0x180028093  jz      short loc_1800280F6
0x180028095  sub     ecx, 1
0x180028098  jz      short loc_1800280D7
0x18002809a  cmp     ecx, 1
0x18002809d  jnz     loc_180028123
0x1800280a3  mov     eax, [rdi+4]
0x1800280a6  mov     [rbx+2Ch], eax
0x1800280a9  mov     edx, [rdi+8]
0x1800280ac  mov     [rbx+30h], edx
0x1800280af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280b6  cmp     rcx, r15
0x1800280b9  jz      short loc_18002812A
0x1800280bb  test    byte ptr [rcx+1Ch], 20h
0x1800280bf  jz      short loc_18002812A
0x1800280c1  mov     rcx, [rcx+10h]
0x1800280c5  mov     r9, rbx
0x1800280c8  mov     [rsp+58h+var_30], edx
0x1800280cc  mov     [rsp+58h+var_38], eax
0x1800280d0  call    WPP_SF_idD
0x1800280d5  jmp     short loc_180028123
0x1800280d7  mov     eax, [rdi+4]
0x1800280da  mov     [rbx+34h], eax
0x1800280dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280e4  cmp     rcx, r15
0x1800280e7  jz      short loc_18002812A
0x1800280e9  test    byte ptr [rcx+1Ch], 20h
0x1800280ed  jz      short loc_18002812A
0x1800280ef  mov     edx, 11h
0x1800280f4  jmp     short loc_180028113
0x1800280f6  mov     eax, [rdi+4]
0x1800280f9  mov     [rbx+38h], eax
0x1800280fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180028103  cmp     rcx, r15
0x180028106  jz      short loc_18002812A
0x180028108  test    byte ptr [rcx+1Ch], 20h
0x18002810c  jz      short loc_18002812A
0x18002810e  mov     edx, 13h
0x180028113  mov     rcx, [rcx+10h]
0x180028117  mov     r9, rbx
0x18002811a  mov     [rsp+58h+var_38], eax
0x18002811e  call    WPP_SF_id
0x180028123  mov     rcx, cs:WPP_GLOBAL_Control
0x18002812a  lea     rdi, WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids
0x180028131  cmp     [rbx+10h], rsi
0x180028135  jz      short loc_180028184
0x180028137  mov     rdx, [rbx+8]; struct __MIDL_DsmRpcNotify_0002 *
0x18002813b  mov     rcx, rbx; this
0x18002813e  call    ?_SupplyNotification@CDevNotify@@AEAAJPEAU__MIDL_DsmRpcNotify_0002@@@Z; CDevNotify::_SupplyNotification(__MIDL_DsmRpcNotify_0002 *)
0x180028143  test    eax, eax
0x180028145  js      short loc_1800281A0
0x180028147  mov     rcx, cs:WPP_GLOBAL_Control
0x18002814e  cmp     rcx, r15
0x180028151  jz      short loc_18002816E
0x180028153  test    byte ptr [rcx+1Ch], 20h
0x180028157  jz      short loc_18002816E
0x180028159  mov     r9, [rbx+10h]
0x18002815d  mov     edx, 14h
0x180028162  mov     rcx, [rcx+10h]
0x180028166  mov     r8, rdi
0x180028169  call    WPP_SF_i
0x18002816e  mov     rsi, [rbx+10h]
0x180028172  mov     qword ptr [rbx+10h], 0
0x18002817a  mov     qword ptr [rbx+8], 0
0x180028182  jmp     short loc_1800281A0
0x180028184  cmp     rcx, r15
0x180028187  jz      short loc_1800281A0
0x180028189  test    byte ptr [rcx+1Ch], 20h
0x18002818d  jz      short loc_1800281A0
0x18002818f  mov     rcx, [rcx+10h]
0x180028193  mov     edx, 15h
0x180028198  mov     r8, rdi
0x18002819b  call    WPP_SF_
0x1800281a0  mov     rcx, rbx; SRWLock
0x1800281a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800281a9  test    rsi, rsi
0x1800281ac  jz      short loc_1800281EE
0x1800281ae  lea     rdx, [rsp+58h+Reply]; Reply
0x1800281b3  mov     [rsp+58h+Reply], 0
0x1800281bb  mov     rcx, rsi; pAsync
0x1800281be  call    cs:__imp_RpcAsyncCompleteCall
0x1800281c4  test    eax, eax
0x1800281c6  jz      short loc_1800281EE
0x1800281c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281cf  cmp     rcx, r15
0x1800281d2  jz      short loc_1800281EE
0x1800281d4  test    byte ptr [rcx+1Ch], 20h
0x1800281d8  jz      short loc_1800281EE
0x1800281da  mov     rcx, [rcx+10h]
0x1800281de  mov     edx, 16h
0x1800281e3  mov     r9d, eax
0x1800281e6  mov     r8, rdi
0x1800281e9  call    WPP_SF_d
0x1800281ee  add     rsp, 38h
0x1800281f2  pop     r15
0x1800281f4  pop     rdi
0x1800281f5  pop     rsi
0x1800281f6  pop     rbx
0x1800281f7  retn
```
