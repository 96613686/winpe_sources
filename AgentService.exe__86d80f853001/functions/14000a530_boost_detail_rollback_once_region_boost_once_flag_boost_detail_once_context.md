# boost::detail::rollback_once_region(boost::once_flag &,boost::detail::once_context &)

- ea: `0x14000a530`
- end: `0x14000a5a0`
- name: `?rollback_once_region@detail@boost@@YAXAEAUonce_flag@2@AEAUonce_context@12@@Z`
- size: `112`
- prototype: `void __fastcall(boost::detail *__hidden this, struct boost::once_flag *, struct boost::detail::once_context *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14008f720`

## callees

- `0x14000a400`
- `0x14000a530`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000a57d`
- `KERNEL32!CloseHandle` at `0x14000a57d`
- `KERNEL32!OpenEventA` at `0x14000a566`
- `KERNEL32!OpenEventA` at `0x14000a566`
- `KERNEL32!SetEvent` at `0x14000a58f`
- `KERNEL32!SetEvent` at `0x14000a58f`

## pseudocode

```c
void __fastcall boost::detail::rollback_once_region(
        boost::detail *this,
        struct boost::once_flag *a2,
        struct boost::detail::once_context *a3)
{
  void *v4; // rbx
  HANDLE v5; // rax
  char *v6; // rcx

  _InterlockedExchange((volatile __int32 *)this, 0);
  v4 = (void *)*((_QWORD *)a2 + 2);
  if ( v4 )
    goto LABEL_7;
  if ( !*((_BYTE *)a2 + 24) )
    boost::detail::name_once_mutex((struct boost::once_flag *)((char *)a2 + 24), (char *)this, a3);
  v5 = OpenEventA(0x100002u, 0, (LPCSTR)a2 + 24);
  v6 = (char *)*((_QWORD *)a2 + 2);
  v4 = v5;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  *((_QWORD *)a2 + 2) = v4;
  if ( v4 )
LABEL_7:
    SetEvent(v4);
}

```

## disassembly

```asm
0x14000a530  mov     [rsp+arg_0], rbx
0x14000a535  push    rdi
0x14000a536  sub     rsp, 20h
0x14000a53a  xor     eax, eax
0x14000a53c  mov     rdi, rdx
0x14000a53f  xchg    eax, [rcx]
0x14000a541  mov     rbx, [rdx+10h]
0x14000a545  test    rbx, rbx
0x14000a548  jnz     short loc_14000A58C
0x14000a54a  cmp     [rdx+18h], bl
0x14000a54d  jnz     short loc_14000A55B
0x14000a54f  mov     rdx, rcx; char *
0x14000a552  lea     rcx, [rdi+18h]; this
0x14000a556  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x14000a55b  lea     r8, [rdi+18h]; lpName
0x14000a55f  xor     edx, edx; bInheritHandle
0x14000a561  mov     ecx, 100002h; dwDesiredAccess
0x14000a566  call    cs:__imp_OpenEventA
0x14000a56c  mov     rcx, [rdi+10h]; hObject
0x14000a570  mov     rbx, rax
0x14000a573  lea     rax, [rcx-1]
0x14000a577  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000a57b  ja      short loc_14000A583
0x14000a57d  call    cs:__imp_CloseHandle
0x14000a583  mov     [rdi+10h], rbx
0x14000a587  test    rbx, rbx
0x14000a58a  jz      short loc_14000A595
0x14000a58c  mov     rcx, rbx; hEvent
0x14000a58f  call    cs:__imp_SetEvent
0x14000a595  mov     rbx, [rsp+28h+arg_0]
0x14000a59a  add     rsp, 20h
0x14000a59e  pop     rdi
0x14000a59f  retn
```
