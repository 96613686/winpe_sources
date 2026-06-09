# ept_cleanup_handle_t_rundown

- ea: `0x1800050c0`
- end: `0x1800051b3`
- name: `ept_cleanup_handle_t_rundown`
- size: `243`
- prototype: `int __fastcall(_QWORD *lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002714`
- `0x1800050c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800050df`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800050df`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005160`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180005160`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800051a3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800051a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005172`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005172`

## pseudocode

```c
int __fastcall ept_cleanup_handle_t_rundown(_QWORD *lpMem)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  __int64 *v4; // r8
  int v5; // r10d
  __int64 v6; // rax
  int result; // eax
  _QWORD *v8; // rbx

  if ( lpMem )
  {
    v2 = 0;
    RtlAcquireSRWLockExclusive(&EpMapRWLock);
    if ( *((_DWORD *)lpMem + 1) )
    {
      v3 = lpMem[1];
      v4 = *(__int64 **)(v3 + 48);
      if ( v3 )
      {
        v5 = cTotalEpEntries;
        do
        {
          if ( *(_QWORD **)(v3 + 40) != lpMem )
            break;
          --*((_DWORD *)lpMem + 1);
          v6 = v3;
          *(_QWORD *)(v3 + 40) = 0;
          v3 = *(_QWORD *)v3;
          --v5;
          *(_QWORD *)v6 = v2;
          v2 = (_QWORD *)v6;
          *(_DWORD *)(v6 + 8) = -1159872290;
        }
        while ( v3 );
        cTotalEpEntries = v5;
      }
      if ( v4 )
        *v4 = v3;
      if ( v3 )
        *(_QWORD *)(v3 + 48) = v4;
      if ( lpMem[1] == IFObjList )
        IFObjList = v3;
    }
    RtlReleaseSRWLockExclusive(&EpMapRWLock);
    result = HeapFree(hEpMapperHeap, 0, lpMem);
    while ( v2 )
    {
      v8 = v2;
      v2 = (_QWORD *)*v2;
      if ( v8[17] )
        RtlUnsubscribeWnfNotificationWaitForCompletion();
      result = CleanupIFOBJNode(v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800050c0  test    rcx, rcx
0x1800050c3  jz      locret_180005187
0x1800050c9  mov     [rsp+arg_0], rbx
0x1800050ce  push    rdi
0x1800050cf  sub     rsp, 20h
0x1800050d3  mov     rbx, rcx
0x1800050d6  xor     edi, edi
0x1800050d8  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x1800050df  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800050e5  cmp     [rbx+4], edi
0x1800050e8  jbe     short loc_180005159
0x1800050ea  mov     rdx, [rbx+8]
0x1800050ee  mov     r8, [rdx+30h]
0x1800050f2  test    rdx, rdx
0x1800050f5  jz      short loc_18000513B
0x1800050f7  mov     r10d, cs:cTotalEpEntries
0x1800050fe  or      r11d, 0FFFFFFFFh
0x180005102  lea     r9, [rdx+28h]
0x180005106  cmp     [r9], rbx
0x180005109  jnz     short loc_180005134
0x18000510b  add     [rbx+4], r11d
0x18000510f  mov     rax, rdx
0x180005112  mov     rcx, rdx
0x180005115  mov     qword ptr [r9], 0
0x18000511c  mov     rdx, [rdx]
0x18000511f  add     r10d, r11d
0x180005122  mov     [rax], rdi
0x180005125  mov     rdi, rax
0x180005128  mov     dword ptr [rax+8], 0BADDC0DEh
0x18000512f  test    rdx, rdx
0x180005132  jnz     short loc_180005102
0x180005134  mov     cs:cTotalEpEntries, r10d
0x18000513b  test    r8, r8
0x18000513e  jz      short loc_180005143
0x180005140  mov     [r8], rdx
0x180005143  test    rdx, rdx
0x180005146  jz      short loc_18000514C
0x180005148  mov     [rdx+30h], r8
0x18000514c  mov     rax, cs:IFObjList
0x180005153  cmp     [rbx+8], rax
0x180005157  jz      short loc_180005188
0x180005159  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x180005160  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180005166  mov     rcx, cs:hEpMapperHeap; hHeap
0x18000516d  mov     r8, rbx; lpMem
0x180005170  xor     edx, edx; dwFlags
0x180005172  call    cs:__imp_HeapFree
0x180005178  test    rdi, rdi
0x18000517b  jnz     short loc_180005191
0x18000517d  mov     rbx, [rsp+28h+arg_0]
0x180005182  add     rsp, 20h
0x180005186  pop     rdi
0x180005187  retn
0x180005188  mov     cs:IFObjList, rdx
0x18000518f  jmp     short loc_180005159
0x180005191  mov     rbx, rdi
0x180005194  mov     rdi, [rdi]
0x180005197  mov     rcx, [rbx+88h]
0x18000519e  test    rcx, rcx
0x1800051a1  jz      short loc_1800051A9
0x1800051a3  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800051a9  mov     rcx, rbx
0x1800051ac  call    CleanupIFOBJNode
0x1800051b1  jmp     short loc_180005178
```
