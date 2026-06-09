# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800036ec`
- end: `0x180003795`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002c40`
- `0x1800034a0`

## callees

- `0x1800036ec`
- `0x180004c74`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall RequestDoWork(__int64 a1, __int64 a2, __int64 *a3, __int64 *a4)
{
  int v6; // esi
  __int64 (__fastcall ***v7)(_QWORD, void *); // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-38h]
  int v13; // [rsp+28h] [rbp-30h]

  v6 = a1;
  if ( (_DWORD)a1 == 0x20000000 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64 *))(*a4 + 48))(a4) )
    {
      v7 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64 *))(*a3 + 56))(a3);
      v8 = (**v7)(v7, s_pModuleContext);
      v9 = v8;
      if ( v8 )
      {
        if ( *(_DWORD *)(v8 + 184) )
        {
          v10 = (*(__int64 (__fastcall **)(__int64 *))(*a4 + 32))(a4);
          if ( v10 )
          {
            *(_QWORD *)(v10 + 32) = *(_QWORD *)(v9 + 168);
            a1 = *(unsigned __int16 *)(v9 + 184);
            LOWORD(a1) = 2 * a1;
            *(_WORD *)(v10 + 4) = a1;
          }
        }
      }
    }
  }
  return AUTH_PROVIDER::DoWork(a1, v6, a3, a4, v12, v13);
}

```

## disassembly

```asm
0x1800036ec  push    rbx
0x1800036ee  push    rsi
0x1800036ef  push    rdi
0x1800036f0  push    r14
0x1800036f2  sub     rsp, 38h
0x1800036f6  mov     rbx, r9
0x1800036f9  mov     r14, r8
0x1800036fc  mov     esi, ecx
0x1800036fe  cmp     ecx, 20000000h
0x180003704  jnz     short loc_18000377E
0x180003706  mov     rax, [r9]
0x180003709  mov     rcx, rbx
0x18000370c  mov     rax, [rax+30h]
0x180003710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003715  test    eax, eax
0x180003717  jz      short loc_18000377E
0x180003719  mov     rax, [r14]
0x18000371c  mov     rcx, r14
0x18000371f  mov     rax, [rax+38h]
0x180003723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003728  mov     rdx, cs:?s_pModuleContext@@3PEAXEA; void * s_pModuleContext
0x18000372f  mov     r8, rax
0x180003732  mov     rcx, [rax]
0x180003735  mov     rax, [rcx]
0x180003738  mov     rcx, r8
0x18000373b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003740  mov     rdi, rax
0x180003743  test    rax, rax
0x180003746  jz      short loc_18000377E
0x180003748  cmp     dword ptr [rax+0B8h], 0
0x18000374f  jz      short loc_18000377E
0x180003751  mov     rcx, [rbx]
0x180003754  mov     rax, [rcx+20h]
0x180003758  mov     rcx, rbx
0x18000375b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003760  test    rax, rax
0x180003763  jz      short loc_18000377E
0x180003765  mov     rcx, [rdi+0A8h]
0x18000376c  mov     [rax+20h], rcx
0x180003770  movzx   ecx, word ptr [rdi+0B8h]
0x180003777  add     cx, cx
0x18000377a  mov     [rax+4], cx
0x18000377e  mov     r9, rbx
0x180003781  mov     r8, r14
0x180003784  mov     edx, esi
0x180003786  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x18000378b  add     rsp, 38h
0x18000378f  pop     r14
0x180003791  pop     rdi
0x180003792  pop     rsi
0x180003793  pop     rbx
0x180003794  retn
```
