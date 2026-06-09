# Threading::CancellationCallback::~CancellationCallback(void)

- ea: `0x180023af4`
- end: `0x180023b77`
- name: `??1CancellationCallback@Threading@@QEAA@XZ`
- size: `131`
- prototype: `void __fastcall(Threading::CancellationCallback *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023b80`

## callees

- `0x180021304`
- `0x180023af4`
- `0x18002c010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180023b00`
- `KERNEL32!TlsGetValue` at `0x180023b2d`
- `KERNEL32!TlsGetValue` at `0x180023b00`
- `KERNEL32!TlsGetValue` at `0x180023b2d`

## pseudocode

```c
void __fastcall Threading::CancellationCallback::~CancellationCallback(Threading::CancellationCallback *this)
{
  __int64 v1; // rax
  _QWORD *Value; // rax
  __int64 v3; // rdx
  char *v4; // rbx
  char *v5; // rcx
  __int64 v6[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( TlsGetValue(dword_18004A6D8) )
  {
    v1 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v1 + 48LL))(v1, v6);
    Value = TlsGetValue(dword_18004A6D8);
    v4 = (char *)(Value + 2);
    v5 = (char *)Value[9];
    if ( v5 )
    {
      LOBYTE(v3) = v5 != v4;
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 32LL))(v5, v3);
      *((_QWORD *)v4 + 7) = 0;
    }
    if ( v6[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6[0] + 24LL))(v6[0]);
  }
}

```

## disassembly

```asm
0x180023af4  push    rbx
0x180023af6  sub     rsp, 30h
0x180023afa  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x180023b00  call    cs:__imp_TlsGetValue
0x180023b06  test    rax, rax
0x180023b09  jz      short loc_180023B71
0x180023b0b  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x180023b10  mov     r8, rax
0x180023b13  mov     rcx, [rax]
0x180023b16  mov     rax, [rcx+30h]
0x180023b1a  lea     rdx, [rsp+38h+var_18]
0x180023b1f  mov     rcx, r8
0x180023b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b27  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x180023b2d  call    cs:__imp_TlsGetValue
0x180023b33  lea     rbx, [rax+10h]
0x180023b37  mov     rcx, [rbx+38h]
0x180023b3b  test    rcx, rcx
0x180023b3e  jz      short loc_180023B5A
0x180023b40  mov     rax, [rcx]
0x180023b43  cmp     rcx, rbx
0x180023b46  setnz   dl
0x180023b49  mov     rax, [rax+20h]
0x180023b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b52  mov     qword ptr [rbx+38h], 0
0x180023b5a  mov     rcx, [rsp+38h+var_18]
0x180023b5f  test    rcx, rcx
0x180023b62  jz      short loc_180023B71
0x180023b64  mov     rax, [rcx]
0x180023b67  mov     rax, [rax+18h]
0x180023b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b70  nop
0x180023b71  add     rsp, 30h
0x180023b75  pop     rbx
0x180023b76  retn
```
