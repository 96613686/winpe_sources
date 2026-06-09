# TransportManager::_ExecuteNextTask(void)

- ea: `0x180004ba0`
- end: `0x180004c41`
- name: `?_ExecuteNextTask@TransportManager@@AEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(TransportManager *this, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800044c4`
- `0x1800044dc`
- `0x180004ba0`
- `0x18000c010`

## string_xrefs

- `0x180004bfc`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::_ExecuteNextTask(TransportManager *this, __int64 a2)
{
  __int64 v3; // rbx
  int v4; // eax
  unsigned int v5; // edi

  if ( !*((_QWORD *)this + 9) )
    Log_AssertionEvent(this, a2, 148);
  v3 = *(_QWORD *)(*((_QWORD *)this + 7) + 16LL);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    return 0;
  }
  else
  {
    Log_HREvent_0((unsigned int)v4, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    return v5;
  }
}

```

## disassembly

```asm
0x180004ba0  mov     [rsp+arg_8], rbx
0x180004ba5  push    rdi
0x180004ba6  sub     rsp, 30h
0x180004baa  mov     rbx, rcx
0x180004bad  cmp     qword ptr [rcx+48h], 0
0x180004bb2  ja      short loc_180004BBF
0x180004bb4  mov     r8d, 94h
0x180004bba  call    Log_AssertionEvent
0x180004bbf  mov     rax, [rbx+38h]
0x180004bc3  mov     rbx, [rax+10h]
0x180004bc7  mov     [rsp+38h+arg_0], rbx
0x180004bcc  test    rbx, rbx
0x180004bcf  jz      short loc_180004BE1
0x180004bd1  mov     rax, [rbx]
0x180004bd4  mov     rcx, rbx
0x180004bd7  mov     rax, [rax+8]
0x180004bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be0  nop
0x180004be1  mov     rax, [rbx]
0x180004be4  mov     rcx, rbx
0x180004be7  mov     rax, [rax+18h]
0x180004beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf0  mov     edi, eax
0x180004bf2  test    eax, eax
0x180004bf4  jns     short loc_180004C24
0x180004bf6  mov     r9d, 97h
0x180004bfc  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180004c03  mov     edx, 1
0x180004c08  mov     ecx, eax
0x180004c0a  call    Log_HREvent_0
0x180004c0f  nop
0x180004c10  mov     rdx, [rbx]
0x180004c13  mov     rcx, rbx
0x180004c16  mov     rax, [rdx+10h]
0x180004c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1f  nop
0x180004c20  mov     eax, edi
0x180004c22  jmp     short loc_180004C36
0x180004c24  mov     rax, [rbx]
0x180004c27  mov     rcx, rbx
0x180004c2a  mov     rax, [rax+10h]
0x180004c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c33  nop
0x180004c34  xor     eax, eax
0x180004c36  mov     rbx, [rsp+38h+arg_8]
0x180004c3b  add     rsp, 30h
0x180004c3f  pop     rdi
0x180004c40  retn
```
