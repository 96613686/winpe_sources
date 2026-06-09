# CThreadRefHost::WaitForRefs(void)

- ea: `0x18000f06c`
- end: `0x18000f0e7`
- name: `?WaitForRefs@CThreadRefHost@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(CThreadRefHost *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800091a0`
- `0x180010204`

## callees

- `0x18000f06c`
- `0x180059010`

## import_xrefs

- `SHCORE!SHSetThreadRef` at `0x18000f077`
- `SHCORE!SHSetThreadRef` at `0x18000f077`
- `USER32!DispatchMessageW` at `0x18000f0d5`
- `USER32!DispatchMessageW` at `0x18000f0d5`
- `USER32!TranslateMessage` at `0x18000f0ca`
- `USER32!TranslateMessage` at `0x18000f0ca`
- `USER32!GetMessageW` at `0x18000f0bb`
- `USER32!GetMessageW` at `0x18000f0bb`

## pseudocode

```c
void __fastcall CThreadRefHost::WaitForRefs(CThreadRefHost *this)
{
  __int64 v2; // rcx
  tagMSG Msg; // [rsp+20h] [rbp-38h] BYREF

  SHSetThreadRef(0);
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
  while ( *((_DWORD *)this + 2) )
  {
    memset(&Msg, 0, sizeof(Msg));
    if ( GetMessageW(&Msg, 0, 0, 0) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
  }
}

```

## disassembly

```asm
0x18000f06c  push    rbx
0x18000f06e  sub     rsp, 50h
0x18000f072  mov     rbx, rcx
0x18000f075  xor     ecx, ecx; punk
0x18000f077  call    cs:__imp_SHSetThreadRef
0x18000f07d  mov     rcx, [rbx+10h]
0x18000f081  test    rcx, rcx
0x18000f084  jz      short loc_18000F0DB
0x18000f086  mov     rax, [rcx]
0x18000f089  mov     rax, [rax+10h]
0x18000f08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f092  mov     qword ptr [rbx+10h], 0
0x18000f09a  jmp     short loc_18000F0DB
0x18000f09c  xorps   xmm0, xmm0
0x18000f09f  lea     rcx, [rsp+58h+Msg]; lpMsg
0x18000f0a4  xor     r9d, r9d; wMsgFilterMax
0x18000f0a7  xor     r8d, r8d; wMsgFilterMin
0x18000f0aa  xor     edx, edx; hWnd
0x18000f0ac  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x18000f0b1  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x18000f0b6  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x18000f0bb  call    cs:__imp_GetMessageW
0x18000f0c1  test    eax, eax
0x18000f0c3  jz      short loc_18000F0DB
0x18000f0c5  lea     rcx, [rsp+58h+Msg]; lpMsg
0x18000f0ca  call    cs:__imp_TranslateMessage
0x18000f0d0  lea     rcx, [rsp+58h+Msg]; lpMsg
0x18000f0d5  call    cs:__imp_DispatchMessageW
0x18000f0db  cmp     dword ptr [rbx+8], 0
0x18000f0df  jnz     short loc_18000F09C
0x18000f0e1  add     rsp, 50h
0x18000f0e5  pop     rbx
0x18000f0e6  retn
```
