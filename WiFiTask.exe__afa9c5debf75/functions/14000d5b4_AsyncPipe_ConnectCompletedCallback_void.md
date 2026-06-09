# AsyncPipe::ConnectCompletedCallback(void)

- ea: `0x14000d5b4`
- end: `0x14000d6b3`
- name: `?ConnectCompletedCallback@AsyncPipe@@AEAAXXZ`
- size: `255`
- prototype: `void __fastcall(_DWORD *pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000d6c0`

## callees

- `0x14000d5b4`
- `0x14000d944`
- `0x14000da74`
- `0x14000e1b4`
- `0x140012010`

## pseudocode

```c
void __fastcall AsyncPipe::ConnectCompletedCallback(_DWORD *pv)
{
  unsigned int v1; // r9d
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v1 = pv[62];
  v3 = v1;
  if ( v1 )
  {
    if ( v1 == 109 || v1 == 232 || v1 == 233 )
    {
LABEL_10:
      v4 = *((_QWORD *)pv + 5);
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *((_QWORD *)pv + 5) = 0;
      }
      v5 = *((_QWORD *)pv + 4);
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + 4) + 16LL))(*((_QWORD *)pv + 4));
        *((_QWORD *)pv + 4) = 0;
      }
      goto LABEL_18;
    }
    v3 = v1 - 535;
    if ( v1 != 535 )
    {
      if ( v1 == 995 )
      {
        AsyncPipe::StartConnect((char *)pv);
        goto LABEL_18;
      }
      if ( v1 != 1223 )
      {
        __FatalError((const char *)pv, 450, "ConnectNamedPipe %u", v1);
        goto LABEL_18;
      }
      goto LABEL_10;
    }
  }
  v6 = *((_QWORD *)pv + 5);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 24LL))(v6, v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + 5) + 16LL))(*((_QWORD *)pv + 5));
    *((_QWORD *)pv + 5) = 0;
  }
  if ( *((_QWORD *)pv + 3) != -1 )
    AsyncPipe::StartRead((char *)pv);
LABEL_18:
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)pv + 24LL))(pv);
}

```

## disassembly

```asm
0x14000d5b4  push    rbx
0x14000d5b6  sub     rsp, 20h
0x14000d5ba  mov     r9d, [rcx+0F8h]; unsigned int
0x14000d5c1  mov     rbx, rcx
0x14000d5c4  mov     edx, r9d
0x14000d5c7  test    r9d, r9d
0x14000d5ca  jz      loc_14000D663
0x14000d5d0  sub     edx, 6Dh ; 'm'
0x14000d5d3  jz      short loc_14000D617
0x14000d5d5  sub     edx, 7Bh ; '{'
0x14000d5d8  jz      short loc_14000D617
0x14000d5da  sub     edx, 1
0x14000d5dd  jz      short loc_14000D617
0x14000d5df  sub     edx, 12Eh
0x14000d5e5  jz      short loc_14000D663
0x14000d5e7  sub     edx, 1CCh
0x14000d5ed  jz      short loc_14000D60D
0x14000d5ef  cmp     edx, 0E4h
0x14000d5f5  jz      short loc_14000D617
0x14000d5f7  lea     r8, aConnectnamedpi; "ConnectNamedPipe %u"
0x14000d5fe  mov     edx, 1C2h; unsigned int
0x14000d603  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d608  jmp     loc_14000D69F
0x14000d60d  call    ?StartConnect@AsyncPipe@@AEAAXXZ; AsyncPipe::StartConnect(void)
0x14000d612  jmp     loc_14000D69F
0x14000d617  mov     rcx, [rcx+28h]
0x14000d61b  test    rcx, rcx
0x14000d61e  jz      short loc_14000D634
0x14000d620  mov     rax, [rcx]
0x14000d623  mov     rax, [rax+10h]
0x14000d627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d62c  mov     qword ptr [rbx+28h], 0
0x14000d634  mov     rcx, [rbx+20h]
0x14000d638  test    rcx, rcx
0x14000d63b  jz      short loc_14000D69F
0x14000d63d  mov     rax, [rcx]
0x14000d640  mov     rax, [rax+20h]
0x14000d644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d649  mov     rcx, [rbx+20h]
0x14000d64d  mov     rax, [rcx]
0x14000d650  mov     rax, [rax+10h]
0x14000d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d659  mov     qword ptr [rbx+20h], 0
0x14000d661  jmp     short loc_14000D69F
0x14000d663  mov     rcx, [rcx+28h]
0x14000d667  test    rcx, rcx
0x14000d66a  jz      short loc_14000D690
0x14000d66c  mov     rax, [rcx]
0x14000d66f  mov     rax, [rax+18h]
0x14000d673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d678  mov     rcx, [rbx+28h]
0x14000d67c  mov     rax, [rcx]
0x14000d67f  mov     rax, [rax+10h]
0x14000d683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d688  mov     qword ptr [rbx+28h], 0
0x14000d690  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x14000d695  jz      short loc_14000D69F
0x14000d697  mov     rcx, rbx; pv
0x14000d69a  call    ?StartRead@AsyncPipe@@AEAAXXZ; AsyncPipe::StartRead(void)
0x14000d69f  mov     rax, [rbx]
0x14000d6a2  mov     rcx, rbx
0x14000d6a5  mov     rax, [rax+18h]
0x14000d6a9  add     rsp, 20h
0x14000d6ad  pop     rbx
0x14000d6ae  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
