# sub_409FEB

- ea: `0x409feb`
- end: `0x40a0cf`
- name: `sub_409FEB`
- size: `228`
- prototype: `_DWORD *__thiscall(int this, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x409aee`

## callees

- `0x4015d2`
- `0x4015fb`
- `0x401fbb`
- `0x402048`
- `0x405ba1`
- `0x409ef8`
- `0x409feb`
- `0x40d08d`

## string_xrefs

- `0x40a007`: `install`
- `0x40a039`: `installsource`

## pseudocode

```c
_DWORD *__thiscall sub_409FEB(int this, _DWORD *a2)
{
  int v3; // esi
  int *v4; // eax
  int v6; // [esp+Ch] [ebp-8h] BYREF

  v6 = 0;
  sub_409EF8(&v6, L"install");
  v3 = v6;
  if ( *(_DWORD *)(v6 - 12) )
  {
    if ( *(_DWORD *)(*(_DWORD *)(this + 20) - 12) )
      sub_405BA1((int)&v6, (int)L" /%s %s", L"installsource", *(_DWORD *)(this + 20));
    if ( *(_DWORD *)(*(_DWORD *)(this + 44) - 12) )
      sub_405BA1((int)&v6, (int)L" /%s \"%s\"", L"sessionid", *(_DWORD *)(this + 44));
    if ( *(_BYTE *)(this + 6) )
      sub_405BA1((int)&v6, (int)L" /%s", L"silent");
    if ( *(_BYTE *)(this + 8) )
      sub_405BA1((int)&v6, (int)L" /%s", L"enterprise");
    v3 = v6;
    *a2 = sub_402048((volatile signed __int32 *)(v6 - 16)) + 4;
  }
  else
  {
    v4 = sub_4015FB();
    sub_401FBB(a2, (int)v4);
  }
  sub_4015D2((volatile signed __int32 *)(v3 - 16));
  return a2;
}

```

## disassembly

```asm
0x409feb  push    ebp
0x409fec  mov     ebp, esp
0x409fee  push    ecx
0x409fef  push    ecx
0x409ff0  mov     eax, ___security_cookie
0x409ff5  xor     eax, ebp
0x409ff7  mov     [ebp+var_4], eax
0x409ffa  and     [ebp+var_8], 0
0x409ffe  lea     eax, [ebp+var_8]
0x40a001  push    ebx
0x40a002  mov     ebx, [ebp+arg_0]
0x40a005  push    esi
0x40a006  push    edi
0x40a007  push    offset aInstall; "install"
0x40a00c  push    eax
0x40a00d  mov     edi, ecx
0x40a00f  call    sub_409EF8
0x40a014  mov     esi, [ebp+var_8]
0x40a017  cmp     dword ptr [esi-0Ch], 0
0x40a01b  jnz     short loc_40A02F
0x40a01d  call    sub_4015FB
0x40a022  push    eax
0x40a023  mov     ecx, ebx
0x40a025  call    sub_401FBB
0x40a02a  jmp     loc_40A0B4
0x40a02f  mov     eax, [edi+14h]
0x40a032  cmp     dword ptr [eax-0Ch], 0
0x40a036  jz      short loc_40A04F
0x40a038  push    eax
0x40a039  push    offset aInstallsource; "installsource"
0x40a03e  lea     eax, [ebp+var_8]
0x40a041  push    offset aSS_1; " /%s %s"
0x40a046  push    eax
0x40a047  call    sub_405BA1
0x40a04c  add     esp, 10h
0x40a04f  mov     eax, [edi+2Ch]
0x40a052  cmp     dword ptr [eax-0Ch], 0
0x40a056  jz      short loc_40A06F
0x40a058  push    eax
0x40a059  push    offset aSessionid; "sessionid"
0x40a05e  lea     eax, [ebp+var_8]
0x40a061  push    offset aSS_2; " /%s \"%s\""
0x40a066  push    eax
0x40a067  call    sub_405BA1
0x40a06c  add     esp, 10h
0x40a06f  cmp     byte ptr [edi+6], 0
0x40a073  mov     esi, offset aS_0; " /%s"
0x40a078  jz      short loc_40A08C
0x40a07a  push    offset aSilent; "silent"
0x40a07f  lea     eax, [ebp+var_8]
0x40a082  push    esi
0x40a083  push    eax
0x40a084  call    sub_405BA1
0x40a089  add     esp, 0Ch
0x40a08c  cmp     byte ptr [edi+8], 0
0x40a090  jz      short loc_40A0A4
0x40a092  push    offset aEnterprise; "enterprise"
0x40a097  lea     eax, [ebp+var_8]
0x40a09a  push    esi
0x40a09b  push    eax
0x40a09c  call    sub_405BA1
0x40a0a1  add     esp, 0Ch
0x40a0a4  mov     esi, [ebp+var_8]
0x40a0a7  lea     ecx, [esi-10h]
0x40a0aa  call    sub_402048
0x40a0af  add     eax, 10h
0x40a0b2  mov     [ebx], eax
0x40a0b4  lea     ecx, [esi-10h]
0x40a0b7  call    sub_4015D2
0x40a0bc  mov     ecx, [ebp+var_4]
0x40a0bf  mov     eax, ebx
0x40a0c1  pop     edi
0x40a0c2  pop     esi
0x40a0c3  xor     ecx, ebp; StackCookie
0x40a0c5  pop     ebx
0x40a0c6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40a0cb  leave
0x40a0cc  retn    4
```
