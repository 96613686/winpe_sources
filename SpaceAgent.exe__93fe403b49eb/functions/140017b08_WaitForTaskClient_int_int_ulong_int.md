# WaitForTaskClient(int,int *,ulong *,int *)

- ea: `0x140017b08`
- end: `0x140017bdc`
- name: `?WaitForTaskClient@@YAHHPEAHPEAK0@Z`
- size: `212`
- prototype: `__int64 __fastcall(__int64, int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140017c58`

## callees

- `0x140017498`
- `0x140017a48`
- `0x140017b08`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x140017b76`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x140017b76`
- `KERNEL32!SetLastError` at `0x140017bc0`
- `KERNEL32!SetLastError` at `0x140017bc0`

## pseudocode

```c
__int64 __fastcall WaitForTaskClient(__int64 a1, int *a2, unsigned int *a3, int *a4)
{
  int v4; // esi
  unsigned int v7; // ebx
  DWORD v8; // eax
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  v7 = Task_ProbePartner((unsigned __int64)&xmmword_140027AA0 & -(__int64)(dword_140027D8C != 0));
  if ( v7 && !*a2 )
  {
    Handles[0] = (HANDLE)GetTaskServerHandle(1u);
    Handles[1] = (HANDLE)GetTaskServerHandle(4u);
    v8 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    switch ( v8 )
    {
      case 0xFFFFFFFF:
        v7 = 0;
        break;
      case 0xC0u:
        v4 = 1;
        break;
      case 1u:
        v7 = Task_ProbePartner((unsigned __int64)&xmmword_140027AA0 & -(__int64)(dword_140027D8C != 0));
        break;
      default:
        if ( v8 )
        {
          v7 = 0;
          SetLastError(0x54Fu);
        }
        break;
    }
  }
  if ( a4 )
    *a4 = v4;
  return v7;
}

```

## disassembly

```asm
0x140017b08  push    rbx
0x140017b0a  push    rbp
0x140017b0b  push    rsi
0x140017b0c  push    rdi
0x140017b0d  push    r13
0x140017b0f  push    r14
0x140017b11  sub     rsp, 48h
0x140017b15  mov     eax, cs:dword_140027D8C
0x140017b1b  lea     r13, xmmword_140027AA0
0x140017b22  xor     esi, esi
0x140017b24  mov     rdi, r9
0x140017b27  neg     eax
0x140017b29  mov     r14, r8
0x140017b2c  mov     rbp, rdx
0x140017b2f  sbb     rcx, rcx
0x140017b32  and     rcx, r13
0x140017b35  call    Task_ProbePartner
0x140017b3a  mov     ebx, eax
0x140017b3c  test    eax, eax
0x140017b3e  jz      loc_140017BC6
0x140017b44  cmp     [rbp+0], esi
0x140017b47  jnz     short loc_140017BC6
0x140017b49  lea     ecx, [rsi+1]; unsigned int
0x140017b4c  call    ?GetTaskServerHandle@@YAPEAXI@Z; GetTaskServerHandle(uint)
0x140017b51  lea     ecx, [rsi+4]; unsigned int
0x140017b54  mov     [rsp+78h+Handles], rax
0x140017b59  call    ?GetTaskServerHandle@@YAPEAXI@Z; GetTaskServerHandle(uint)
0x140017b5e  lea     ecx, [rsi+2]; nCount
0x140017b61  mov     [rsp+78h+var_40], rax
0x140017b66  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140017b6a  mov     [rsp+78h+bAlertable], esi; bAlertable
0x140017b6e  xor     r8d, r8d; bWaitAll
0x140017b71  lea     rdx, [rsp+78h+Handles]; lpHandles
0x140017b76  call    cs:__imp_WaitForMultipleObjectsEx
0x140017b7c  cmp     eax, 0FFFFFFFFh
0x140017b7f  jnz     short loc_140017B85
0x140017b81  xor     ebx, ebx
0x140017b83  jmp     short loc_140017BC6
0x140017b85  cmp     eax, 0C0h
0x140017b8a  jnz     short loc_140017B93
0x140017b8c  mov     esi, 1
0x140017b91  jmp     short loc_140017BC6
0x140017b93  cmp     eax, 1
0x140017b96  jnz     short loc_140017BB5
0x140017b98  mov     eax, cs:dword_140027D8C
0x140017b9e  mov     r8, r14
0x140017ba1  neg     eax
0x140017ba3  mov     rdx, rbp
0x140017ba6  sbb     rcx, rcx
0x140017ba9  and     rcx, r13
0x140017bac  call    Task_ProbePartner
0x140017bb1  mov     ebx, eax
0x140017bb3  jmp     short loc_140017BC6
0x140017bb5  test    eax, eax
0x140017bb7  jz      short loc_140017BC6
0x140017bb9  xor     ebx, ebx
0x140017bbb  mov     ecx, 54Fh; dwErrCode
0x140017bc0  call    cs:__imp_SetLastError
0x140017bc6  test    rdi, rdi
0x140017bc9  jz      short loc_140017BCD
0x140017bcb  mov     [rdi], esi
0x140017bcd  mov     eax, ebx
0x140017bcf  add     rsp, 48h
0x140017bd3  pop     r14
0x140017bd5  pop     r13
0x140017bd7  pop     rdi
0x140017bd8  pop     rsi
0x140017bd9  pop     rbp
0x140017bda  pop     rbx
0x140017bdb  retn
```
