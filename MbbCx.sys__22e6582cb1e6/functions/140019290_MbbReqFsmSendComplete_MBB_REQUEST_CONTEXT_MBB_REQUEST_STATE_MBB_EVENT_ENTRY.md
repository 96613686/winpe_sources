# MbbReqFsmSendComplete(_MBB_REQUEST_CONTEXT *,MBB_REQUEST_STATE,_MBB_EVENT_ENTRY *)

- ea: `0x140019290`
- end: `0x14001935f`
- name: `?MbbReqFsmSendComplete@@YAXPEAU_MBB_REQUEST_CONTEXT@@W4MBB_REQUEST_STATE@@PEAU_MBB_EVENT_ENTRY@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018ce0`
- `0x140019210`
- `0x14001a9ec`

## callees

- `0x140019290`
- `0x140019f78`
- `0x14001b760`
- `0x140047e90`

## pseudocode

```c
void __fastcall MbbReqFsmSendComplete(__int64 a1, __int64 a2, __int64 a3)
{
  char v4; // si
  int v6; // eax
  void (__fastcall *v7)(_QWORD, __int64, _QWORD); // rax
  _DWORD *v8; // rax

  v4 = *(_BYTE *)(a1 + 488);
  if ( *(_DWORD *)(a3 + 32) )
  {
    v6 = *(_DWORD *)(a1 + 620);
    *(_OWORD *)(a1 + 704) = *(_OWORD *)(a1 + 604);
    *(_DWORD *)(a1 + 720) = v6;
  }
  v7 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 544);
  if ( v7 )
    v7(**(_QWORD **)(a1 + 48), a1, *(unsigned int *)(a3 + 32));
  if ( *(_BYTE *)(a1 + 464) )
  {
    v8 = *(_DWORD **)(a1 + 80);
    if ( !v8 || *v8 != 234946852 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01031 + 2104))(
        WdfDriverGlobals,
        *(_QWORD *)(a1 + 480),
        *(unsigned int *)(a3 + 32));
    goto LABEL_10;
  }
  if ( v4 == 1 )
LABEL_10:
    MbxMessagesHandler(*(struct _MBB_REQUEST_MANAGER **)(a1 + 48), (void *)1, 0, 0);
  MbbReqMgrDerefRequest((struct _MBB_REQUEST_CONTEXT *)a1);
}

```

## disassembly

```asm
0x140019290  mov     [rsp+arg_0], rbx
0x140019295  mov     [rsp+arg_8], rsi
0x14001929a  push    rdi
0x14001929b  sub     rsp, 20h
0x14001929f  cmp     dword ptr [r8+20h], 0
0x1400192a4  mov     rdi, r8
0x1400192a7  mov     sil, [rcx+1E8h]
0x1400192ae  mov     rbx, rcx
0x1400192b1  jz      short loc_1400192CD
0x1400192b3  movups  xmm0, xmmword ptr [rcx+25Ch]
0x1400192ba  mov     eax, [rcx+26Ch]
0x1400192c0  movups  xmmword ptr [rcx+2C0h], xmm0
0x1400192c7  mov     [rcx+2D0h], eax
0x1400192cd  mov     rax, [rcx+220h]
0x1400192d4  test    rax, rax
0x1400192d7  jz      short loc_1400192EC
0x1400192d9  mov     rcx, [rcx+30h]
0x1400192dd  mov     rdx, rbx
0x1400192e0  mov     r8d, [r8+20h]
0x1400192e4  mov     rcx, [rcx]
0x1400192e7  call    _guard_dispatch_icall
0x1400192ec  cmp     byte ptr [rbx+1D0h], 0
0x1400192f3  jz      short loc_14001932D
0x1400192f5  mov     rax, [rbx+50h]
0x1400192f9  test    rax, rax
0x1400192fc  jz      short loc_140019306
0x1400192fe  cmp     dword ptr [rax], 0E010124h
0x140019304  jz      short loc_140019333
0x140019306  mov     rax, cs:WdfFunctions_01031
0x14001930d  mov     r8d, [rdi+20h]
0x140019311  mov     rdx, [rbx+1E0h]
0x140019318  mov     rcx, cs:WdfDriverGlobals
0x14001931f  mov     rax, [rax+838h]
0x140019326  call    _guard_dispatch_icall
0x14001932b  jmp     short loc_140019333
0x14001932d  cmp     sil, 1
0x140019331  jnz     short loc_140019346
0x140019333  mov     rcx, [rbx+30h]; struct _MBB_REQUEST_MANAGER *
0x140019337  xor     r9d, r9d; void *
0x14001933a  xor     r8d, r8d; void *
0x14001933d  lea     edx, [r9+1]; void *
0x140019341  call    ?MbxMessagesHandler@@YAXPEAX000@Z; MbxMessagesHandler(void *,void *,void *,void *)
0x140019346  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140019349  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x14001934e  mov     rbx, [rsp+28h+arg_0]
0x140019353  mov     rsi, [rsp+28h+arg_8]
0x140019358  add     rsp, 20h
0x14001935c  pop     rdi
0x14001935d  retn
```
