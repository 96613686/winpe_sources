# CDocument::OnUpdateFileSendMail(CCmdUI *)

- ea: `0x180026110`
- end: `0x180026208`
- name: `?OnUpdateFileSendMail@CDocument@@IEAAXPEAVCCmdUI@@@Z`
- size: `248`
- prototype: `void __fastcall(CDocument *__hidden this, struct CCmdUI *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x180026110`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002615f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002615f`
- `KERNEL32!GetProfileIntW` at `0x18002613c`
- `KERNEL32!GetProfileIntW` at `0x18002613c`
- `USER32!GetMenuState` at `0x1800261a5`
- `USER32!GetMenuState` at `0x1800261b9`
- `USER32!GetMenuState` at `0x1800261a5`
- `USER32!GetMenuState` at `0x1800261b9`
- `USER32!RemoveMenu` at `0x1800261cb`
- `USER32!RemoveMenu` at `0x1800261f7`
- `USER32!RemoveMenu` at `0x1800261cb`
- `USER32!RemoveMenu` at `0x1800261f7`

## string_xrefs

- `0x18002614b`: `MAPI32.DLL`

## pseudocode

```c
void __fastcall CDocument::OnUpdateFileSendMail(CDocument *this, UINT *a2)
{
  DWORD v3; // eax
  int v4; // edx
  __int64 v5; // rdi
  UINT MenuState; // ebp
  UINT v7; // esi
  UINT v8; // edx

  if ( _afxIsMailAvail == -1 )
  {
    if ( !GetProfileIntW(L"MAIL", L"MAPI", 0) || (v3 = SearchPathW(0, L"MAPI32.DLL", 0, 0, 0, 0), v4 = 1, !v3) )
      v4 = 0;
    _afxIsMailAvail = v4;
  }
  (**(void (__fastcall ***)(struct CCmdUI *))a2)((struct CCmdUI *)a2);
  if ( !_afxIsMailAvail )
  {
    v5 = *((_QWORD *)a2 + 2);
    if ( v5 )
    {
      MenuState = GetMenuState(*(HMENU *)(v5 + 8), a2[3] - 1, 0x400u);
      v7 = GetMenuState(*(HMENU *)(v5 + 8), a2[3] + 1, 0x400u);
      RemoveMenu(*(HMENU *)(v5 + 8), a2[3], 0x400u);
      if ( ((unsigned __int16)MenuState & (unsigned __int16)v7 & 0x800) != 0 )
      {
        if ( MenuState == -1 )
        {
          if ( v7 == -1 )
            return;
          v8 = a2[3];
        }
        else
        {
          v8 = a2[3] - 1;
        }
        RemoveMenu(*(HMENU *)(v5 + 8), v8, 0x400u);
      }
    }
  }
}

```

## disassembly

```asm
0x180026110  push    rbx
0x180026112  push    rbp
0x180026113  push    rsi
0x180026114  push    rdi
0x180026115  push    r15
0x180026117  sub     rsp, 30h
0x18002611b  mov     rbx, rdx
0x18002611e  xor     esi, esi
0x180026120  mov     edx, cs:?_afxIsMailAvail@@3HA; int _afxIsMailAvail
0x180026126  cmp     edx, 0FFFFFFFFh
0x180026129  jnz     short loc_180026174
0x18002612b  xor     r8d, r8d; nDefault
0x18002612e  lea     rdx, KeyName; "MAPI"
0x180026135  lea     rcx, AppName; "MAIL"
0x18002613c  call    cs:__imp_GetProfileIntW
0x180026142  test    eax, eax
0x180026144  jz      short loc_18002616C
0x180026146  mov     [rsp+58h+lpFilePart], rsi; lpFilePart
0x18002614b  lea     rdx, FileName; "MAPI32.DLL"
0x180026152  xor     r9d, r9d; nBufferLength
0x180026155  mov     [rsp+58h+lpBuffer], rsi; lpBuffer
0x18002615a  xor     r8d, r8d; lpExtension
0x18002615d  xor     ecx, ecx; lpPath
0x18002615f  call    cs:__imp_SearchPathW
0x180026165  lea     edx, [rsi+1]
0x180026168  test    eax, eax
0x18002616a  jnz     short loc_18002616E
0x18002616c  mov     edx, esi
0x18002616e  mov     cs:?_afxIsMailAvail@@3HA, edx; int _afxIsMailAvail
0x180026174  mov     rax, [rbx]
0x180026177  mov     rcx, rbx
0x18002617a  mov     rax, [rax]
0x18002617d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026182  cmp     cs:?_afxIsMailAvail@@3HA, esi; int _afxIsMailAvail
0x180026188  jnz     short loc_1800261FD
0x18002618a  mov     rdi, [rbx+10h]
0x18002618e  test    rdi, rdi
0x180026191  jz      short loc_1800261FD
0x180026193  mov     edx, [rbx+0Ch]
0x180026196  mov     r15d, 400h
0x18002619c  mov     rcx, [rdi+8]; hMenu
0x1800261a0  dec     edx; uId
0x1800261a2  mov     r8d, r15d; uFlags
0x1800261a5  call    cs:__imp_GetMenuState
0x1800261ab  mov     edx, [rbx+0Ch]
0x1800261ae  mov     r8d, r15d; uFlags
0x1800261b1  mov     rcx, [rdi+8]; hMenu
0x1800261b5  inc     edx; uId
0x1800261b7  mov     ebp, eax
0x1800261b9  call    cs:__imp_GetMenuState
0x1800261bf  mov     edx, [rbx+0Ch]; uPosition
0x1800261c2  mov     r8d, r15d; uFlags
0x1800261c5  mov     rcx, [rdi+8]; hMenu
0x1800261c9  mov     esi, eax
0x1800261cb  call    cs:__imp_RemoveMenu
0x1800261d1  mov     ecx, esi
0x1800261d3  and     ecx, ebp
0x1800261d5  bt      ecx, 0Bh
0x1800261d9  jnb     short loc_1800261FD
0x1800261db  or      eax, 0FFFFFFFFh
0x1800261de  cmp     ebp, eax
0x1800261e0  jz      short loc_1800261E9
0x1800261e2  mov     edx, [rbx+0Ch]
0x1800261e5  dec     edx
0x1800261e7  jmp     short loc_1800261F0
0x1800261e9  cmp     esi, eax
0x1800261eb  jz      short loc_1800261FD
0x1800261ed  mov     edx, [rbx+0Ch]; uPosition
0x1800261f0  mov     rcx, [rdi+8]; hMenu
0x1800261f4  mov     r8d, r15d; uFlags
0x1800261f7  call    cs:__imp_RemoveMenu
0x1800261fd  add     rsp, 30h
0x180026201  pop     r15
0x180026203  pop     rdi
0x180026204  pop     rsi
0x180026205  pop     rbp
0x180026206  pop     rbx
0x180026207  retn
```
