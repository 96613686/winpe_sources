# FwppInjectEpilogue

- ea: `0x180003048`
- end: `0x1800032dc`
- name: `FwppInjectEpilogue`
- size: `660`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001600`
- `0x180001cd0`
- `0x180002280`
- `0x1800025b0`
- `0x180002910`

## callees

- `0x180001600`
- `0x180001cd0`
- `0x180002280`
- `0x1800025b0`
- `0x180002910`
- `0x180003048`
- `0x18000a224`
- `0x180020400`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180003115`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180003115`
- `NETIO!WfpCalloutDiagTraceInjectionEpilogue` at `0x1800030ff`
- `NETIO!WfpCalloutDiagTraceInjectionEpilogue` at `0x1800030ff`

## pseudocode

```c
void __fastcall FwppInjectEpilogue()
{
  __int64 v0; // rax
  __int64 v1; // rsi
  __int64 v2; // rdi
  void **v3; // r14
  unsigned int *v4; // rbx
  void **v5; // rax
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ebp
  __int64 v13; // r8

  LODWORD(v0) = HIDWORD(KeGetPcr()[1].LockArray);
  _InterlockedDecrement(&gFwpTcpIp);
  v1 = gPerProcessorContext;
  v2 = 3 * v0;
  if ( !*(_BYTE *)(gPerProcessorContext + 24 * v0 + 1) )
  {
    *(_WORD *)(gPerProcessorContext + 24 * v0) = 256;
    v3 = (void **)(v1 + 8 + 24 * v0);
    while ( 1 )
    {
      v4 = (unsigned int *)*v3;
      if ( *v3 == v3 )
      {
        *(_BYTE *)(v1 + 8 * v2 + 1) = 0;
        return;
      }
      if ( *((void ***)v4 + 1) != v3 || (v5 = *(void ***)v4, *(unsigned int **)(*(_QWORD *)v4 + 8LL) != v4) )
        __fastfail(3u);
      *v3 = v5;
      v5[1] = v3;
      v6 = v4[5];
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              if ( v9 != 1 )
                goto LABEL_13;
              v11 = FwppInjectTransportSendAsync(
                      1,
                      *((_QWORD *)v4 + 3),
                      *((_QWORD *)v4 + 4),
                      *((_QWORD *)v4 + 11),
                      v4[10],
                      (unsigned __int64)(v4 + 24) & -(__int64)(*((_BYTE *)v4 + 144) != 0),
                      *((_WORD *)v4 + 22),
                      v4[12],
                      *((_QWORD *)v4 + 7),
                      *((_QWORD *)v4 + 8),
                      *((_QWORD *)v4 + 9));
            }
            else
            {
              v11 = FwpsInjectTransportReceiveAsync0(
                      *((HANDLE *)v4 + 3),
                      *((HANDLE *)v4 + 4),
                      *((PVOID *)v4 + 19),
                      v4[10],
                      *((_WORD *)v4 + 22),
                      (COMPARTMENT_ID)v4[12],
                      v4[13],
                      v4[20],
                      *((NET_BUFFER_LIST **)v4 + 7),
                      *((FWPS_INJECT_COMPLETE0 *)v4 + 8),
                      *((HANDLE *)v4 + 9));
            }
          }
          else
          {
            v11 = FwpsInjectForwardAsync0(
                    *((HANDLE *)v4 + 3),
                    *((HANDLE *)v4 + 4),
                    v4[10],
                    *((_WORD *)v4 + 22),
                    (COMPARTMENT_ID)v4[12],
                    v4[13],
                    *((NET_BUFFER_LIST **)v4 + 7),
                    *((FWPS_INJECT_COMPLETE0 *)v4 + 8),
                    *((HANDLE *)v4 + 9));
          }
        }
        else
        {
          v11 = FwpsInjectNetworkSendAsync0(
                  *((HANDLE *)v4 + 3),
                  *((HANDLE *)v4 + 4),
                  v4[10],
                  (COMPARTMENT_ID)v4[12],
                  *((NET_BUFFER_LIST **)v4 + 7),
                  *((FWPS_INJECT_COMPLETE0 *)v4 + 8),
                  *((HANDLE *)v4 + 9));
        }
      }
      else
      {
        v11 = FwpsInjectNetworkReceiveAsync0(
                *((HANDLE *)v4 + 3),
                *((HANDLE *)v4 + 4),
                v4[10],
                (COMPARTMENT_ID)v4[12],
                v4[13],
                v4[20],
                *((NET_BUFFER_LIST **)v4 + 7),
                *((FWPS_INJECT_COMPLETE0 *)v4 + 8),
                *((HANDLE *)v4 + 9));
      }
      v12 = v11;
      if ( v11 < 0 )
      {
        FwppUndoNetBufferListInjectionChanges(*((_QWORD *)v4 + 7));
        LOBYTE(v13) = 1;
        *(_DWORD *)(*((_QWORD *)v4 + 7) + 140LL) = v12;
        (*((void (__fastcall **)(_QWORD, _QWORD, __int64))v4 + 8))(*((_QWORD *)v4 + 9), *((_QWORD *)v4 + 7), v13);
        *((_QWORD *)v4 + 7) = 0;
      }
LABEL_13:
      *(_BYTE *)(v1 + 8 * v2) = 0;
      v10 = *((_QWORD *)v4 + 3);
      _InterlockedDecrement((volatile signed __int32 *)(v10 + 40));
      _InterlockedAdd(&gFwpTcpIp, 0xFFFFFFFE);
      WfpCalloutDiagTraceInjectionEpilogue(*(_QWORD *)(v10 + 88), v4[5]);
      ExFreeToNPagedLookasideList(&Lookaside, v4);
    }
  }
}

```

## disassembly

```asm
0x180003048  push    rbx
0x18000304a  push    rbp
0x18000304b  push    rsi
0x18000304c  push    rdi
0x18000304d  push    r14
0x18000304f  sub     rsp, 60h
0x180003053  mov     eax, gs:1A4h
0x18000305b  lock dec cs:gFwpTcpIp
0x180003062  mov     rsi, cs:gPerProcessorContext
0x180003069  lea     rdi, [rax+rax*2]
0x18000306d  cmp     byte ptr [rsi+rdi*8+1], 0
0x180003072  jnz     short loc_18000308F
0x180003074  lea     r14, [rsi+8]
0x180003078  mov     word ptr [rsi+rdi*8], 100h
0x18000307e  lea     r14, [r14+rdi*8]
0x180003082  mov     rbx, [r14]
0x180003085  cmp     rbx, r14
0x180003088  jnz     short loc_18000309B
0x18000308a  mov     byte ptr [rsi+rdi*8+1], 0
0x18000308f  add     rsp, 60h
0x180003093  pop     r14
0x180003095  pop     rdi
0x180003096  pop     rsi
0x180003097  pop     rbp
0x180003098  pop     rbx
0x180003099  retn
0x18000309b  cmp     [rbx+8], r14
0x18000309f  jnz     loc_1800032D5
0x1800030a5  mov     rax, [rbx]
0x1800030a8  cmp     [rax+8], rbx
0x1800030ac  jnz     loc_1800032D5
0x1800030b2  mov     [r14], rax
0x1800030b5  mov     [rax+8], r14
0x1800030b9  mov     ecx, [rbx+14h]
0x1800030bc  test    ecx, ecx
0x1800030be  jz      loc_180003292
0x1800030c4  sub     ecx, 1
0x1800030c7  jz      loc_18000325D
0x1800030cd  sub     ecx, 1
0x1800030d0  jz      loc_180003219
0x1800030d6  sub     ecx, 1
0x1800030d9  jz      loc_1800031C3
0x1800030df  cmp     ecx, 1
0x1800030e2  jz      short loc_180003126
0x1800030e4  mov     byte ptr [rsi+rdi*8], 0
0x1800030e8  mov     rcx, [rbx+18h]
0x1800030ec  lock dec dword ptr [rcx+28h]
0x1800030f0  lock add cs:gFwpTcpIp, 0FFFFFFFEh
0x1800030f8  mov     edx, [rbx+14h]
0x1800030fb  mov     rcx, [rcx+58h]
0x1800030ff  call    cs:__imp_WfpCalloutDiagTraceInjectionEpilogue
0x180003106  nop     dword ptr [rax+rax+00h]
0x18000310b  mov     rdx, rbx; Entry
0x18000310e  lea     rcx, Lookaside; Lookaside
0x180003115  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000311c  nop     dword ptr [rax+rax+00h]
0x180003121  jmp     loc_180003082
0x180003126  mov     al, [rbx+90h]
0x18000312c  lea     rcx, [rbx+60h]
0x180003130  mov     r9, [rbx+58h]
0x180003134  neg     al
0x180003136  mov     rax, [rbx+48h]
0x18000313a  mov     r8, [rbx+20h]
0x18000313e  sbb     rdx, rdx
0x180003141  mov     [rsp+88h+completionContext], rax
0x180003146  and     rdx, rcx
0x180003149  mov     rax, [rbx+40h]
0x18000314d  mov     ecx, 1
0x180003152  mov     [rsp+88h+completionFn], rax
0x180003157  mov     rax, [rbx+38h]
0x18000315b  mov     [rsp+88h+netBufferList], rax
0x180003160  mov     eax, [rbx+30h]
0x180003163  mov     [rsp+88h+subInterfaceIndex], eax
0x180003167  movzx   eax, word ptr [rbx+2Ch]
0x18000316b  mov     word ptr [rsp+88h+interfaceIndex], ax
0x180003170  mov     eax, [rbx+28h]
0x180003173  mov     qword ptr [rsp+88h+compartmentId], rdx
0x180003178  mov     rdx, [rbx+18h]
0x18000317c  mov     dword ptr [rsp+88h+addressFamily], eax
0x180003180  call    FwppInjectTransportSendAsync
0x180003185  mov     ebp, eax
0x180003187  test    eax, eax
0x180003189  jns     loc_1800030E4
0x18000318f  mov     rcx, [rbx+38h]
0x180003193  call    FwppUndoNetBufferListInjectionChanges
0x180003198  mov     rax, [rbx+38h]
0x18000319c  mov     r8b, 1
0x18000319f  mov     [rax+8Ch], ebp
0x1800031a5  mov     rax, [rbx+40h]
0x1800031a9  mov     rdx, [rbx+38h]
0x1800031ad  mov     rcx, [rbx+48h]
0x1800031b1  call    _guard_dispatch_icall
0x1800031b6  mov     qword ptr [rbx+38h], 0
0x1800031be  jmp     loc_1800030E4
0x1800031c3  mov     rax, [rbx+48h]
0x1800031c7  mov     r9d, [rbx+28h]; flags
0x1800031cb  mov     r8, [rbx+98h]; reserved
0x1800031d2  mov     rdx, [rbx+20h]; injectionContext
0x1800031d6  mov     rcx, [rbx+18h]; injectionHandle
0x1800031da  mov     [rsp+88h+completionContext], rax; completionContext
0x1800031df  mov     rax, [rbx+40h]
0x1800031e3  mov     [rsp+88h+completionFn], rax; completionFn
0x1800031e8  mov     rax, [rbx+38h]
0x1800031ec  mov     [rsp+88h+netBufferList], rax; netBufferList
0x1800031f1  mov     eax, [rbx+50h]
0x1800031f4  mov     [rsp+88h+subInterfaceIndex], eax; subInterfaceIndex
0x1800031f8  mov     eax, [rbx+34h]
0x1800031fb  mov     [rsp+88h+interfaceIndex], eax; interfaceIndex
0x1800031ff  mov     eax, [rbx+30h]
0x180003202  mov     [rsp+88h+compartmentId], eax; compartmentId
0x180003206  movzx   eax, word ptr [rbx+2Ch]
0x18000320a  mov     [rsp+88h+addressFamily], ax; addressFamily
0x18000320f  call    FwpsInjectTransportReceiveAsync0
0x180003214  jmp     loc_180003185
0x180003219  mov     rax, [rbx+48h]
0x18000321d  movzx   r9d, word ptr [rbx+2Ch]; addressFamily
0x180003222  mov     r8d, [rbx+28h]; flags
0x180003226  mov     rdx, [rbx+20h]; injectionContext
0x18000322a  mov     rcx, [rbx+18h]; injectionHandle
0x18000322e  mov     [rsp+88h+netBufferList], rax; completionContext
0x180003233  mov     rax, [rbx+40h]
0x180003237  mov     qword ptr [rsp+88h+subInterfaceIndex], rax; completionFn
0x18000323c  mov     rax, [rbx+38h]
0x180003240  mov     qword ptr [rsp+88h+interfaceIndex], rax; netBufferList
0x180003245  mov     eax, [rbx+34h]
0x180003248  mov     [rsp+88h+compartmentId], eax; interfaceIndex
0x18000324c  mov     eax, [rbx+30h]
0x18000324f  mov     dword ptr [rsp+88h+addressFamily], eax; compartmentId
0x180003253  call    FwpsInjectForwardAsync0
0x180003258  jmp     loc_180003185
0x18000325d  mov     rax, [rbx+48h]
0x180003261  mov     r9d, [rbx+30h]; compartmentId
0x180003265  mov     r8d, [rbx+28h]; flags
0x180003269  mov     rdx, [rbx+20h]; injectionContext
0x18000326d  mov     rcx, [rbx+18h]; injectionHandle
0x180003271  mov     qword ptr [rsp+88h+interfaceIndex], rax; completionContext
0x180003276  mov     rax, [rbx+40h]
0x18000327a  mov     qword ptr [rsp+88h+compartmentId], rax; completionFn
0x18000327f  mov     rax, [rbx+38h]
0x180003283  mov     qword ptr [rsp+88h+addressFamily], rax; netBufferList
0x180003288  call    FwpsInjectNetworkSendAsync0
0x18000328d  jmp     loc_180003185
0x180003292  mov     rax, [rbx+48h]
0x180003296  mov     r9d, [rbx+30h]; compartmentId
0x18000329a  mov     r8d, [rbx+28h]; flags
0x18000329e  mov     rdx, [rbx+20h]; injectionContext
0x1800032a2  mov     rcx, [rbx+18h]; injectionHandle
0x1800032a6  mov     [rsp+88h+netBufferList], rax; completionContext
0x1800032ab  mov     rax, [rbx+40h]
0x1800032af  mov     qword ptr [rsp+88h+subInterfaceIndex], rax; completionFn
0x1800032b4  mov     rax, [rbx+38h]
0x1800032b8  mov     qword ptr [rsp+88h+interfaceIndex], rax; netBufferList
0x1800032bd  mov     eax, [rbx+50h]
0x1800032c0  mov     [rsp+88h+compartmentId], eax; subInterfaceIndex
0x1800032c4  mov     eax, [rbx+34h]
0x1800032c7  mov     dword ptr [rsp+88h+addressFamily], eax; interfaceIndex
0x1800032cb  call    FwpsInjectNetworkReceiveAsync0
0x1800032d0  jmp     loc_180003185
0x1800032d5  mov     ecx, 3
0x1800032da  int     29h; Win8: RtlFailFast(ecx)
```
