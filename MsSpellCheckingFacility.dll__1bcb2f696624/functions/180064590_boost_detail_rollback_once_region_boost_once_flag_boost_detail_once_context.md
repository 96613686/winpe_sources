# boost::detail::rollback_once_region(boost::once_flag &,boost::detail::once_context &)

- ea: `0x180064590`
- end: `0x180064600`
- name: `?rollback_once_region@detail@boost@@YAXAEAUonce_flag@2@AEAUonce_context@12@@Z`
- size: `112`
- prototype: `void __fastcall(boost::detail *__hidden this, struct boost::once_flag *, struct boost::detail::once_context *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800bd120`

## callees

- `0x1800643a0`
- `0x180064590`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800645dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800645dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800645ef`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800645ef`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1800645c6`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1800645c6`

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
0x180064590  mov     [rsp+arg_0], rbx
0x180064595  push    rdi
0x180064596  sub     rsp, 20h
0x18006459a  xor     eax, eax
0x18006459c  mov     rdi, rdx
0x18006459f  xchg    eax, [rcx]
0x1800645a1  mov     rbx, [rdx+10h]
0x1800645a5  test    rbx, rbx
0x1800645a8  jnz     short loc_1800645EC
0x1800645aa  cmp     [rdx+18h], bl
0x1800645ad  jnz     short loc_1800645BB
0x1800645af  mov     rdx, rcx; char *
0x1800645b2  lea     rcx, [rdi+18h]; this
0x1800645b6  call    ?name_once_mutex@detail@boost@@YAXPEADPEAX@Z; boost::detail::name_once_mutex(char *,void *)
0x1800645bb  lea     r8, [rdi+18h]; lpName
0x1800645bf  xor     edx, edx; bInheritHandle
0x1800645c1  mov     ecx, 100002h; dwDesiredAccess
0x1800645c6  call    cs:__imp_OpenEventA
0x1800645cc  mov     rcx, [rdi+10h]; hObject
0x1800645d0  mov     rbx, rax
0x1800645d3  lea     rax, [rcx-1]
0x1800645d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800645db  ja      short loc_1800645E3
0x1800645dd  call    cs:__imp_CloseHandle
0x1800645e3  mov     [rdi+10h], rbx
0x1800645e7  test    rbx, rbx
0x1800645ea  jz      short loc_1800645F5
0x1800645ec  mov     rcx, rbx; hEvent
0x1800645ef  call    cs:__imp_SetEvent
0x1800645f5  mov     rbx, [rsp+28h+arg_0]
0x1800645fa  add     rsp, 20h
0x1800645fe  pop     rdi
0x1800645ff  retn
```
