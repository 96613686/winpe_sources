# XMLNode_GetChildTag

- ea: `0x1800116c0`
- end: `0x1800117a5`
- name: `XMLNode_GetChildTag`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800117b0`

## callees

- `0x180011480`
- `0x180011510`
- `0x1800116c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall XMLNode_GetChildTag(__int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *), __int64 a2, _QWORD *a3)
{
  __int64 (__fastcall **v5)(_QWORD, GUID *, __int64 *); // rax
  int ElementsByTagName; // ebx
  int Child; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+20h] BYREF

  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v5 = *a1;
  v12 = 0;
  ElementsByTagName = (*v5)(a1, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v12);
  if ( ElementsByTagName >= 0 )
  {
    v11 = 0;
    ElementsByTagName = XMLElem_GetElementsByTagName(v12, a2, &v11);
    if ( ElementsByTagName >= 0 )
    {
      Child = XMLNodeList_GetChild(v11, 0, a3);
      v8 = v11;
      ElementsByTagName = Child;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    v9 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  return (unsigned int)ElementsByTagName;
}

```

## disassembly

```asm
0x1800116c0  mov     r11, rsp
0x1800116c3  mov     [r11+10h], rbx
0x1800116c7  mov     [r11+18h], rsi
0x1800116cb  push    rdi
0x1800116cc  sub     rsp, 20h
0x1800116d0  mov     rdi, r8
0x1800116d3  mov     rsi, rdx
0x1800116d6  test    rcx, rcx
0x1800116d9  jz      loc_180011790
0x1800116df  test    rdx, rdx
0x1800116e2  jz      loc_180011790
0x1800116e8  test    r8, r8
0x1800116eb  jz      loc_180011790
0x1800116f1  mov     qword ptr [r8], 0
0x1800116f8  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800116ff  mov     rax, [rcx]
0x180011702  lea     r8, [r11+20h]
0x180011706  mov     qword ptr [r11+20h], 0
0x18001170e  mov     rax, [rax]
0x180011711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011716  mov     ebx, eax
0x180011718  test    eax, eax
0x18001171a  js      short loc_18001178C
0x18001171c  mov     rcx, [rsp+28h+arg_18]
0x180011721  lea     r8, [rsp+28h+arg_0]
0x180011726  mov     rdx, rsi
0x180011729  mov     [rsp+28h+arg_0], 0
0x180011732  call    XMLElem_GetElementsByTagName
0x180011737  mov     ebx, eax
0x180011739  test    eax, eax
0x18001173b  js      short loc_18001176D
0x18001173d  mov     rcx, [rsp+28h+arg_0]
0x180011742  mov     r8, rdi
0x180011745  xor     edx, edx
0x180011747  call    XMLNodeList_GetChild
0x18001174c  mov     rcx, [rsp+28h+arg_0]
0x180011751  mov     ebx, eax
0x180011753  test    rcx, rcx
0x180011756  jz      short loc_18001176D
0x180011758  mov     [rsp+28h+arg_0], 0
0x180011761  mov     rax, [rcx]
0x180011764  mov     rax, [rax+10h]
0x180011768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001176d  mov     rcx, [rsp+28h+arg_18]
0x180011772  test    rcx, rcx
0x180011775  jz      short loc_18001178C
0x180011777  mov     [rsp+28h+arg_18], 0
0x180011780  mov     rax, [rcx]
0x180011783  mov     rax, [rax+10h]
0x180011787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001178c  mov     eax, ebx
0x18001178e  jmp     short loc_180011795
0x180011790  mov     eax, 80070057h
0x180011795  mov     rbx, [rsp+28h+arg_8]
0x18001179a  mov     rsi, [rsp+28h+arg_10]
0x18001179f  add     rsp, 20h
0x1800117a3  pop     rdi
0x1800117a4  retn
```
