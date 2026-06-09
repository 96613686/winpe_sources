# CWMIBroker::Connect(IWbemServices * *)

- ea: `0x14000304c`
- end: `0x1400030ef`
- name: `?Connect@CWMIBroker@@AEAAJPEAPEAUIWbemServices@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(const OLECHAR **this, struct IWbemServices **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140003320`

## callees

- `0x14000304c`
- `0x1400030f8`
- `0x140004c84`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400030bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400030bf`

## pseudocode

```c
__int64 __fastcall CWMIBroker::Connect(const OLECHAR **this, struct IWbemServices **a2)
{
  int v5; // ebx
  struct IWbemServices *v6; // rbp
  DWORD CurrentProcessId; // eax
  struct IWbemServices *v8; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147749896LL;
  v8 = 0;
  v5 = CWMIBroker::ConnectToNamespace(this, (struct IUnknown **)&v8);
  if ( v5 >= 0 )
  {
    v6 = v8;
    v5 = (*((__int64 (__fastcall **)(const OLECHAR **, struct IWbemServices *))*this + 1))(this, v8);
    if ( v5 >= 0 )
    {
      *a2 = v6;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        CurrentProcessId = GetCurrentProcessId();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_39117c5435fe322648485e64dab1d1d4_Traceguids,
          CurrentProcessId);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000304c  push    rbx
0x14000304e  push    rbp
0x14000304f  push    rsi
0x140003050  push    rdi
0x140003051  sub     rsp, 28h
0x140003055  mov     rdi, rdx
0x140003058  mov     rsi, rcx
0x14000305b  test    rdx, rdx
0x14000305e  jnz     short loc_140003067
0x140003060  mov     eax, 80041008h
0x140003065  jmp     short loc_1400030E6
0x140003067  lea     rdx, [rsp+48h+arg_8]; struct IWbemServices **
0x14000306c  mov     [rsp+48h+arg_8], 0
0x140003075  call    ?ConnectToNamespace@CWMIBroker@@AEAAJPEAPEAUIWbemServices@@@Z; CWMIBroker::ConnectToNamespace(IWbemServices * *)
0x14000307a  mov     ebx, eax
0x14000307c  test    eax, eax
0x14000307e  js      short loc_1400030E4
0x140003080  mov     rax, [rsi]
0x140003083  mov     rcx, rsi
0x140003086  mov     rbp, [rsp+48h+arg_8]
0x14000308b  mov     rdx, rbp
0x14000308e  mov     rax, [rax+8]
0x140003092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003097  mov     ebx, eax
0x140003099  test    eax, eax
0x14000309b  js      short loc_1400030E4
0x14000309d  mov     [rdi], rbp
0x1400030a0  mov     rax, cs:WPP_GLOBAL_Control
0x1400030a7  lea     rcx, WPP_GLOBAL_Control
0x1400030ae  cmp     rax, rcx
0x1400030b1  jz      short loc_1400030E4
0x1400030b3  test    byte ptr [rax+1Ch], 1
0x1400030b7  jz      short loc_1400030E4
0x1400030b9  cmp     byte ptr [rax+19h], 5
0x1400030bd  jb      short loc_1400030E4
0x1400030bf  call    cs:__imp_GetCurrentProcessId
0x1400030c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030cc  lea     r8, WPP_39117c5435fe322648485e64dab1d1d4_Traceguids
0x1400030d3  mov     edx, 0Ah
0x1400030d8  mov     r9d, eax
0x1400030db  mov     rcx, [rcx+10h]
0x1400030df  call    WPP_SF_d
0x1400030e4  mov     eax, ebx
0x1400030e6  add     rsp, 28h
0x1400030ea  pop     rdi
0x1400030eb  pop     rsi
0x1400030ec  pop     rbp
0x1400030ed  pop     rbx
0x1400030ee  retn
```
