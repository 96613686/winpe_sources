# ServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x180001410`
- end: `0x1800014b0`
- name: `?ServiceControlHandler@@YAKKKPEAX0@Z`
- size: `160`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180001410`
- `0x180001a44`
- `0x18000aa18`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ServiceControlHandler(DWORD dwControl, DWORD dwEventType, _QWORD *lpEventData, _QWORD **lpContext)
{
  wil::details *v6; // rcx
  DWORD v7; // ecx
  void *v8; // rdx

  if ( dwControl == 4 )
    return 0;
  v7 = dwControl - 1;
  if ( v7 )
  {
    if ( v7 == 32 )
    {
      if ( dwEventType == 5 )
      {
        (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*lpContext[10] + 56LL))(
          lpContext[10],
          *((unsigned int *)lpEventData + 1),
          lpEventData[1]);
      }
      else if ( dwEventType == 6 )
      {
        (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*lpContext[10] + 64LL))(
          lpContext[10],
          *((unsigned int *)lpEventData + 1),
          lpEventData[1]);
      }
      return 0;
    }
    return 120;
  }
  else
  {
    if ( (int)ServiceContext::ReportStatus((ServiceContext *)lpContext, 3, 0, 1000) >= 0 )
    {
      v6 = (wil::details *)lpContext[3];
      if ( v6 )
      {
        *((_BYTE *)lpContext + 21) = 1;
        wil::details::SetEvent(v6, v8);
      }
      return 0;
    }
    return 1066;
  }
}

```

## disassembly

```asm
0x180001410  push    rbx
0x180001412  sub     rsp, 20h
0x180001416  mov     rbx, r9
0x180001419  mov     r9, r8
0x18000141c  cmp     ecx, 4
0x18000141f  jnz     short loc_18000143D
0x180001421  xor     eax, eax
0x180001423  add     rsp, 20h
0x180001427  pop     rbx
0x180001428  retn
0x180001429  mov     rcx, [rbx+18h]; this
0x18000142d  test    rcx, rcx
0x180001430  jz      short loc_180001421
0x180001432  mov     byte ptr [rbx+15h], 1
0x180001436  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000143b  jmp     short loc_180001421
0x18000143d  sub     ecx, 1
0x180001440  jz      short loc_18000148C
0x180001442  cmp     ecx, 20h ; ' '
0x180001445  jz      short loc_18000144E
0x180001447  mov     eax, 78h ; 'x'
0x18000144c  jmp     short loc_180001423
0x18000144e  cmp     edx, 5
0x180001451  jnz     short loc_18000146D
0x180001453  mov     rcx, [rbx+50h]
0x180001457  mov     r8, [r8+8]
0x18000145b  mov     edx, [r9+4]
0x18000145f  mov     rax, [rcx]
0x180001462  mov     rax, [rax+38h]
0x180001466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000146b  jmp     short loc_180001421
0x18000146d  cmp     edx, 6
0x180001470  jnz     short loc_180001421
0x180001472  mov     rcx, [rbx+50h]
0x180001476  mov     r8, [r8+8]
0x18000147a  mov     edx, [r9+4]
0x18000147e  mov     rax, [rcx]
0x180001481  mov     rax, [rax+40h]
0x180001485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000148a  jmp     short loc_180001421
0x18000148c  mov     r9d, 3E8h; unsigned int
0x180001492  xor     r8d, r8d; int
0x180001495  mov     edx, 3; unsigned int
0x18000149a  mov     rcx, rbx; this
0x18000149d  call    ?ReportStatus@ServiceContext@@QEAAJKJK@Z; ServiceContext::ReportStatus(ulong,long,ulong)
0x1800014a2  test    eax, eax
0x1800014a4  jns     short loc_180001429
0x1800014a6  mov     eax, 42Ah
0x1800014ab  jmp     loc_180001423
```
