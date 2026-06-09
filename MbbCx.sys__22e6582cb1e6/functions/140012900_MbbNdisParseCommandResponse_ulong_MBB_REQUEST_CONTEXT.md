# MbbNdisParseCommandResponse(ulong,_MBB_REQUEST_CONTEXT *)

- ea: `0x140012900`
- end: `0x140012a23`
- name: `?MbbNdisParseCommandResponse@@YAHKPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(int, struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140012c90`

## callees

- `0x140012900`
- `0x1400138d0`
- `0x1400193bc`
- `0x140019f78`
- `0x14001a234`
- `0x14001a9ec`
- `0x14001abec`

## pseudocode

```c
__int64 __fastcall MbbNdisParseCommandResponse(int a1, struct _MBB_REQUEST_CONTEXT *a2)
{
  struct _MBB_REQUEST_MANAGER *v2; // rbp
  unsigned int v3; // r14d
  struct _MBB_COMMAND_FRAGMENT_HEADER *v5; // r15
  __int64 v7; // rdx
  struct _MBB_REASSEMBLE_CONTEXT *v8; // rsi
  __int64 v9; // r8
  struct _MBB_REQUEST_CONTEXT *RequestByKey; // rax
  struct _MBB_REQUEST_CONTEXT *v11; // r8
  __int64 v12; // rbx
  unsigned int v13; // edi
  struct _GUID v15; // [rsp+30h] [rbp-48h] BYREF

  v2 = (struct _MBB_REQUEST_MANAGER *)*((_QWORD *)a2 + 6);
  v3 = *((_DWORD *)a2 + 165);
  v5 = (struct _MBB_COMMAND_FRAGMENT_HEADER *)*((_QWORD *)a2 + 81);
  v15 = *(struct _GUID *)((char *)a2 + 24);
  v8 = MbbReqMgrAcquireSharedReassembleContext(v2, v5, v3, &v15);
  if ( v8 )
  {
    RequestByKey = MbbReqMgrGetRequestByKey(v2, v7, v9, a1);
    v11 = RequestByKey;
    v12 = (__int64)RequestByKey;
    if ( !RequestByKey )
      v11 = a2;
    v15 = *(struct _GUID *)((char *)v11 + 24);
    v13 = MbbNdisReassembleResponseFragment((unsigned __int8 *)v5, v3, v8, RequestByKey != 0, v2, &v15);
    if ( v13 != 259 )
    {
      if ( v12 )
      {
        *(_OWORD *)(v12 + 648) = *(_OWORD *)v8;
        *(_OWORD *)(v12 + 664) = *((_OWORD *)v8 + 1);
        *(_OWORD *)(v12 + 680) = *((_OWORD *)v8 + 2);
        *(_OWORD *)(v12 + 696) = *((_OWORD *)v8 + 3);
        *(_OWORD *)(v12 + 712) = *((_OWORD *)v8 + 4);
        MbbReqMgrQueueEvent((__int64)v2, v12, 4, *(_QWORD *)(v12 + 664), *(_DWORD *)(v12 + 680));
      }
      MbbReqMgrReleaseSharedReassembleContext(v2);
    }
    if ( v12 )
      MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)v12);
  }
  else
  {
    return (unsigned int)-1073676267;
  }
  return v13;
}

```

## disassembly

```asm
0x140012900  push    rbx
0x140012902  push    rbp
0x140012903  push    rsi
0x140012904  push    rdi
0x140012905  push    r14
0x140012907  push    r15
0x140012909  sub     rsp, 48h
0x14001290d  movups  xmm0, xmmword ptr [rdx+18h]
0x140012911  mov     rbp, [rdx+30h]
0x140012915  lea     r9, [rsp+78h+var_48]; struct _GUID
0x14001291a  mov     r14d, [rdx+294h]
0x140012921  mov     rdi, rdx
0x140012924  mov     r15, [rdx+288h]
0x14001292b  mov     ebx, ecx
0x14001292d  mov     r8d, r14d; unsigned int
0x140012930  mov     rdx, r15; struct _MBB_COMMAND_FRAGMENT_HEADER *
0x140012933  mov     rcx, rbp; struct _MBB_REQUEST_MANAGER *
0x140012936  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x14001293c  call    ?MbbReqMgrAcquireSharedReassembleContext@@YAPEAU_MBB_REASSEMBLE_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@PEAU_MBB_COMMAND_FRAGMENT_HEADER@@KU_GUID@@@Z; MbbReqMgrAcquireSharedReassembleContext(_MBB_REQUEST_MANAGER *,_MBB_COMMAND_FRAGMENT_HEADER *,ulong,_GUID)
0x140012941  mov     rsi, rax
0x140012944  test    rax, rax
0x140012947  jz      loc_140012A0E
0x14001294d  mov     r9d, ebx; unsigned int
0x140012950  mov     rcx, rbp; struct _MBB_REQUEST_MANAGER *
0x140012953  call    ?MbbReqMgrGetRequestByKey@@YAPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_REQUEST_MANAGER@@KKKPEAU_NDIS_OID_REQUEST@@@Z; MbbReqMgrGetRequestByKey(_MBB_REQUEST_MANAGER *,ulong,ulong,ulong,_NDIS_OID_REQUEST *)
0x140012958  test    rax, rax
0x14001295b  mov     r8, rax
0x14001295e  mov     rbx, rax
0x140012961  mov     edx, r14d; unsigned int
0x140012964  cmovz   r8, rdi
0x140012968  lea     rax, [rsp+78h+var_48]
0x14001296d  mov     [rsp+78h+var_50], rax; struct _GUID *
0x140012972  setnz   r9b; unsigned __int8
0x140012976  mov     rcx, r15; unsigned __int8 *
0x140012979  mov     [rsp+78h+var_58], rbp; struct _MBB_REQUEST_MANAGER *
0x14001297e  movups  xmm0, xmmword ptr [r8+18h]
0x140012983  mov     r8, rsi; struct _MBB_REASSEMBLE_CONTEXT *
0x140012986  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x14001298c  call    ?MbbNdisReassembleResponseFragment@@YAHPEAEKPEAU_MBB_REASSEMBLE_CONTEXT@@EPEAU_MBB_REQUEST_MANAGER@@U_GUID@@@Z; MbbNdisReassembleResponseFragment(uchar *,ulong,_MBB_REASSEMBLE_CONTEXT *,uchar,_MBB_REQUEST_MANAGER *,_GUID)
0x140012991  mov     edi, eax
0x140012993  cmp     eax, 103h
0x140012998  jz      short loc_1400129FF
0x14001299a  test    rbx, rbx
0x14001299d  jz      short loc_1400129F7
0x14001299f  movups  xmm0, xmmword ptr [rsi]
0x1400129a2  mov     r8d, 4
0x1400129a8  mov     rdx, rbx
0x1400129ab  mov     rcx, rbp
0x1400129ae  movups  xmmword ptr [rbx+288h], xmm0
0x1400129b5  movups  xmm1, xmmword ptr [rsi+10h]
0x1400129b9  movups  xmmword ptr [rbx+298h], xmm1
0x1400129c0  movups  xmm0, xmmword ptr [rsi+20h]
0x1400129c4  movups  xmmword ptr [rbx+2A8h], xmm0
0x1400129cb  movups  xmm1, xmmword ptr [rsi+30h]
0x1400129cf  movups  xmmword ptr [rbx+2B8h], xmm1
0x1400129d6  movups  xmm0, xmmword ptr [rsi+40h]
0x1400129da  movups  xmmword ptr [rbx+2C8h], xmm0
0x1400129e1  mov     eax, [rbx+2A8h]
0x1400129e7  mov     r9, [rbx+298h]
0x1400129ee  mov     dword ptr [rsp+78h+var_58], eax
0x1400129f2  call    ?MbbReqMgrQueueEvent@@YAXPEAU_MBB_REQUEST_MANAGER@@PEAU_MBB_REQUEST_CONTEXT@@W4MBB_REQUEST_EVENT@@PEAXK@Z; MbbReqMgrQueueEvent(_MBB_REQUEST_MANAGER *,_MBB_REQUEST_CONTEXT *,MBB_REQUEST_EVENT,void *,ulong)
0x1400129f7  mov     rcx, rbp; struct _MBB_REQUEST_MANAGER *
0x1400129fa  call    ?MbbReqMgrReleaseSharedReassembleContext@@YAXPEAU_MBB_REQUEST_MANAGER@@@Z; MbbReqMgrReleaseSharedReassembleContext(_MBB_REQUEST_MANAGER *)
0x1400129ff  test    rbx, rbx
0x140012a02  jz      short loc_140012A13
0x140012a04  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140012a07  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x140012a0c  jmp     short loc_140012A13
0x140012a0e  mov     edi, 0C0010015h
0x140012a13  mov     eax, edi
0x140012a15  add     rsp, 48h
0x140012a19  pop     r15
0x140012a1b  pop     r14
0x140012a1d  pop     rdi
0x140012a1e  pop     rsi
0x140012a1f  pop     rbp
0x140012a20  pop     rbx
0x140012a21  retn
```
