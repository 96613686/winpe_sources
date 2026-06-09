# AddComponent(_objectinfo *,ushort *,ushort *)

- ea: `0x180016234`
- end: `0x1800162fa`
- name: `?AddComponent@@YAJPEAU_objectinfo@@PEAG1@Z`
- size: `198`
- prototype: `int(struct _objectinfo *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016630`

## callees

- `0x180016234`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180016268`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180016268`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x18001629c`
- `ACTIVEDS!__imp_ReallocADsMem` at `0x18001629c`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800162bf`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800162bf`

## pseudocode

```c
__int64 __fastcall AddComponent(struct _objectinfo *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  void *v5; // rcx
  LPVOID v6; // rax
  _DWORD *v7; // rdi
  int v8; // edx

  if ( a2 && *a2 )
  {
    v5 = (void *)*((_QWORD *)a1 + 69);
    if ( v5 )
    {
      v8 = *((_DWORD *)a1 + 137);
      v7 = (_DWORD *)((char *)a1 + 544);
      if ( *((_DWORD *)a1 + 136) != v8 )
      {
LABEL_10:
        *(_QWORD *)(*((_QWORD *)a1 + 69) + 16LL * (unsigned int)*v7) = AllocADsStr(a2);
        *(_QWORD *)(*((_QWORD *)a1 + 69) + 16LL * (unsigned int)(*v7)++ + 8) = 0;
        return 0;
      }
      v6 = ReallocADsMem(v5, 16 * v8, 16 * v8 + 512);
      if ( !v6 )
        return 2147942414LL;
      *((_DWORD *)a1 + 137) += 32;
    }
    else
    {
      v6 = AllocADsMem(0x200u);
      *((_DWORD *)a1 + 137) = 32;
      v7 = (_DWORD *)((char *)a1 + 544);
    }
    *((_QWORD *)a1 + 69) = v6;
    goto LABEL_10;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180016234  push    rbx
0x180016236  push    rbp
0x180016237  push    rsi
0x180016238  push    rdi
0x180016239  sub     rsp, 28h
0x18001623d  xor     ebp, ebp
0x18001623f  mov     rsi, rdx
0x180016242  mov     rbx, rcx
0x180016245  test    rdx, rdx
0x180016248  jz      loc_1800162EC
0x18001624e  cmp     [rdx], bp
0x180016251  jz      loc_1800162EC
0x180016257  mov     rcx, [rcx+228h]; pOldMem
0x18001625e  test    rcx, rcx
0x180016261  jnz     short loc_180016281
0x180016263  mov     ecx, 200h; cb
0x180016268  call    cs:__imp_AllocADsMem
0x18001626e  mov     dword ptr [rbx+224h], 20h ; ' '
0x180016278  lea     rdi, [rbx+220h]
0x18001627f  jmp     short loc_1800162B5
0x180016281  mov     edx, [rbx+224h]
0x180016287  lea     rdi, [rbx+220h]
0x18001628e  cmp     [rdi], edx
0x180016290  jnz     short loc_1800162BC
0x180016292  shl     edx, 4; cbOld
0x180016295  lea     r8d, [rdx+200h]; cbNew
0x18001629c  call    cs:__imp_ReallocADsMem
0x1800162a2  test    rax, rax
0x1800162a5  jnz     short loc_1800162AE
0x1800162a7  mov     eax, 8007000Eh
0x1800162ac  jmp     short loc_1800162F1
0x1800162ae  add     dword ptr [rbx+224h], 20h ; ' '
0x1800162b5  mov     [rbx+228h], rax
0x1800162bc  mov     rcx, rsi; pStr
0x1800162bf  call    cs:__imp_AllocADsStr
0x1800162c5  mov     edx, [rdi]
0x1800162c7  mov     rcx, [rbx+228h]
0x1800162ce  add     rdx, rdx
0x1800162d1  mov     [rcx+rdx*8], rax
0x1800162d5  mov     ecx, [rdi]
0x1800162d7  mov     rax, [rbx+228h]
0x1800162de  add     rcx, rcx
0x1800162e1  mov     [rax+rcx*8+8], rbp
0x1800162e6  inc     dword ptr [rdi]
0x1800162e8  xor     eax, eax
0x1800162ea  jmp     short loc_1800162F1
0x1800162ec  mov     eax, 80004005h
0x1800162f1  add     rsp, 28h
0x1800162f5  pop     rdi
0x1800162f6  pop     rsi
0x1800162f7  pop     rbp
0x1800162f8  pop     rbx
0x1800162f9  retn
```
