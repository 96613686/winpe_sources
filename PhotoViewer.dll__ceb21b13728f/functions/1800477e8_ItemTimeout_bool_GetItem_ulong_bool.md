# ItemTimeout<bool>::GetItem(ulong,bool *)

- ea: `0x1800477e8`
- end: `0x1800478bb`
- name: `?GetItem@?$ItemTimeout@_N@@QEAAJKPEA_N@Z`
- size: `211`
- prototype: `__int64 __fastcall(Base::RefCountBaseMultiThreaded *this, DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800471a4`

## callees

- `0x180027fe4`
- `0x1800477e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180047860`
- `KERNEL32!GetLastError` at `0x180047860`
- `KERNEL32!WaitForSingleObject` at `0x18004787b`
- `KERNEL32!WaitForSingleObject` at `0x18004787b`
- `KERNEL32!CloseHandle` at `0x18004789f`
- `KERNEL32!CloseHandle` at `0x18004789f`
- `KERNEL32!CreateThread` at `0x180047845`
- `KERNEL32!CreateThread` at `0x180047845`

## pseudocode

```c
__int64 __fastcall ItemTimeout<bool>::GetItem(Base::RefCountBaseMultiThreaded *this, DWORD dwMilliseconds, _BYTE *a3)
{
  HANDLE v7; // rax
  void *v8; // rdi
  unsigned int v9; // esi
  DWORD ThreadId; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147500035LL;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  ThreadId = 0;
  v7 = CreateThread(0, 0, ItemTimeout<bool>::ThreadProc, this, 0, &ThreadId);
  v8 = v7;
  if ( v7 )
  {
    v9 = -2147023436;
    if ( !WaitForSingleObject(v7, dwMilliseconds) )
    {
      *a3 = *((_BYTE *)this + 20);
      v9 = *((_DWORD *)this + 4);
    }
    CloseHandle(v8);
    return v9;
  }
  else
  {
    Base::RefCountBaseMultiThreaded::BaseRelease(this);
    return (unsigned __int16)GetLastError() | 0x80070000;
  }
}

```

## disassembly

```asm
0x1800477e8  mov     [rsp+arg_0], rbx
0x1800477ed  mov     [rsp+arg_8], rsi
0x1800477f2  push    rdi
0x1800477f3  push    r14
0x1800477f5  push    r15
0x1800477f7  sub     rsp, 50h
0x1800477fb  mov     r14, r8
0x1800477fe  mov     r15d, edx
0x180047801  mov     rbx, rcx
0x180047804  test    r8, r8
0x180047807  jnz     short loc_180047813
0x180047809  mov     eax, 80004003h
0x18004780e  jmp     loc_1800478A7
0x180047813  lock inc dword ptr [rcx+8]
0x180047817  mov     [rsp+68h+ThreadId], 0
0x180047822  lea     rax, [rsp+68h+ThreadId]
0x18004782a  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18004782f  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180047837  mov     r9, rbx; lpParameter
0x18004783a  lea     r8, ?ThreadProc@?$ItemTimeout@_N@@CAKPEAX@Z; lpStartAddress
0x180047841  xor     edx, edx; dwStackSize
0x180047843  xor     ecx, ecx; lpThreadAttributes
0x180047845  call    cs:__imp_CreateThread
0x18004784b  mov     rdi, rax
0x18004784e  mov     [rsp+68h+var_38], rax
0x180047853  test    rax, rax
0x180047856  jnz     short loc_180047870
0x180047858  mov     rcx, rbx; this
0x18004785b  call    ?BaseRelease@RefCountBaseMultiThreaded@Base@@QEAAKXZ; Base::RefCountBaseMultiThreaded::BaseRelease(void)
0x180047860  call    cs:__imp_GetLastError
0x180047866  movzx   eax, ax
0x180047869  or      eax, 80070000h
0x18004786e  jmp     short loc_1800478A7
0x180047870  mov     esi, 800705B4h
0x180047875  mov     edx, r15d; dwMilliseconds
0x180047878  mov     rcx, rax; hHandle
0x18004787b  call    cs:__imp_WaitForSingleObject
0x180047881  test    eax, eax
0x180047883  jnz     short loc_18004789C
0x180047885  mov     al, [rbx+14h]
0x180047888  mov     [r14], al
0x18004788b  mov     esi, [rbx+10h]
0x18004788e  jmp     short loc_18004789C
0x180047890  mov     rdi, [rsp+68h+var_38]
0x180047895  mov     esi, [rsp+68h+arg_18]
0x18004789c  mov     rcx, rdi; hObject
0x18004789f  call    cs:__imp_CloseHandle
0x1800478a5  mov     eax, esi
0x1800478a7  mov     rbx, [rsp+68h+arg_0]
0x1800478ac  mov     rsi, [rsp+68h+arg_8]
0x1800478b1  add     rsp, 50h
0x1800478b5  pop     r15
0x1800478b7  pop     r14
0x1800478b9  pop     rdi
0x1800478ba  retn
```
