# WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies::GetCallerIdentity(void)

- ea: `0x1800073e0`
- end: `0x180007481`
- name: `?GetCallerIdentity@RequestManagerDesktopDependencies@ManagerDLL@OTS@WpcDesktop@@EEBA?AVSid@@XZ`
- size: `161`
- prototype: `void *__fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800073e0`
- `0x180027878`
- `0x180027e70`
- `0x1800284b8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000746d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000746d`

## pseudocode

```c
void *__fastcall WpcDesktop::OTS::ManagerDLL::RequestManagerDesktopDependencies::GetCallerIdentity(
        __int64 a1,
        void *a2)
{
  _QWORD *v3; // rax
  volatile signed __int32 *v4; // rbx
  _QWORD *v6; // [rsp+28h] [rbp-20h] BYREF
  volatile signed __int32 *v7; // [rsp+30h] [rbp-18h]
  HANDLE hObject; // [rsp+58h] [rbp+10h] BYREF

  hObject = a2;
  v3 = (_QWORD *)Token::FromComClient(&hObject);
  anonymous_namespace_::GetInformation__TOKEN_USER_1_(&v6, *v3);
  Sid::FromPSID(a2, *v6);
  v4 = v7;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return a2;
}

```

## disassembly

```asm
0x1800073e0  mov     [rsp+arg_0], rbx
0x1800073e5  mov     [rsp+hObject], rdx
0x1800073ea  push    rdi
0x1800073eb  sub     rsp, 40h
0x1800073ef  mov     rdi, rdx
0x1800073f2  lea     rcx, [rsp+48h+hObject]
0x1800073f7  call    ?FromComClient@Token@@SA?AV1@_N@Z; Token::FromComClient(bool)
0x1800073fc  nop
0x1800073fd  mov     rdx, [rax]
0x180007400  lea     rcx, [rsp+48h+var_20]
0x180007405  call    _anonymous_namespace___GetInformation__TOKEN_USER_1_
0x18000740a  nop
0x18000740b  mov     rdx, [rsp+48h+var_20]
0x180007410  mov     rdx, [rdx]
0x180007413  mov     rcx, rdi
0x180007416  call    ?FromPSID@Sid@@SA?AV1@PEAX@Z; Sid::FromPSID(void *)
0x18000741b  nop
0x18000741c  mov     rbx, [rsp+48h+var_18]
0x180007421  test    rbx, rbx
0x180007424  jz      short loc_18000745E
0x180007426  or      eax, 0FFFFFFFFh
0x180007429  lock xadd [rbx+8], eax
0x18000742e  cmp     eax, 1
0x180007431  jnz     short loc_18000745E
0x180007433  mov     rax, [rbx]
0x180007436  mov     rcx, rbx
0x180007439  mov     rax, [rax]
0x18000743c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007441  or      eax, 0FFFFFFFFh
0x180007444  lock xadd [rbx+0Ch], eax
0x180007449  cmp     eax, 1
0x18000744c  jnz     short loc_18000745E
0x18000744e  mov     rax, [rbx]
0x180007451  mov     rcx, rbx
0x180007454  mov     rax, [rax+8]
0x180007458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000745d  nop
0x18000745e  mov     rcx, [rsp+48h+hObject]; hObject
0x180007463  lea     rax, [rcx-1]
0x180007467  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000746b  ja      short loc_180007473
0x18000746d  call    cs:__imp_CloseHandle
0x180007473  mov     rax, rdi
0x180007476  mov     rbx, [rsp+48h+arg_0]
0x18000747b  add     rsp, 40h
0x18000747f  pop     rdi
0x180007480  retn
```
