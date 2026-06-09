# CVaultCredential::IsCredConstructionComplete(void)

- ea: `0x1800118e0`
- end: `0x180011a8d`
- name: `?IsCredConstructionComplete@CVaultCredential@@AEAAEXZ`
- size: `429`
- prototype: `unsigned __int8 __fastcall(CVaultCredential *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800111c0`

## callees

- `0x180003140`
- `0x1800118e0`
- `0x18004d010`

## pseudocode

```c
unsigned __int8 __fastcall CVaultCredential::IsCredConstructionComplete(CVaultCredential *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rax
  unsigned int v5; // eax
  __int64 v6; // rsi
  unsigned int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+30h] [rbp-18h]
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v9 = 0;
  v10 = 0;
  v8 = 0;
  v11 = 0;
  if ( !*((_DWORD *)this + 52)
    && *(_BYTE *)(*((_QWORD *)this + 4) + 56LL)
    && *(_BYTE *)(*((_QWORD *)this + 5) + 56LL)
    && ((v3 = *((_QWORD *)this + 3)) == 0 || *(_BYTE *)(v3 + 56))
    && *((_DWORD *)this + 36) == *((unsigned __int16 *)this + 74)
    && !(*(unsigned int (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)this + 1) + 88LL))(
          *((_QWORD *)this + 1),
          &v9,
          &v11) )
  {
    v5 = v11;
    if ( *((_WORD *)this + 74) != (_WORD)v11 )
    {
      while ( v2 < v5 )
      {
        v6 = 8LL * v2;
        v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + v9) + 8LL))(*(_QWORD *)(v6 + v9));
        if ( !(*(__int64 (__fastcall **)(CVaultCredential *, _QWORD))(*(_QWORD *)this + 136LL))(this, v7)
          && ((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + v9) + 32LL))(*(_QWORD *)(v6 + v9)) & 8) == 0 )
        {
          goto LABEL_8;
        }
        ++v2;
        v5 = v11;
      }
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v8);
    return 1;
  }
  else
  {
LABEL_8:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v8);
    return 0;
  }
}

```

## disassembly

```asm
0x1800118e0  mov     [rsp+arg_8], rbx
0x1800118e5  mov     [rsp+arg_10], rsi
0x1800118ea  push    rdi
0x1800118eb  sub     rsp, 40h
0x1800118ef  mov     rdi, rcx
0x1800118f2  xor     ebx, ebx
0x1800118f4  mov     [rsp+48h+var_20], rbx
0x1800118f9  mov     [rsp+48h+var_18], ebx
0x1800118fd  mov     [rsp+48h+var_28], rbx
0x180011902  mov     [rsp+48h+arg_0], ebx
0x180011906  cmp     [rcx+0D0h], ebx
0x18001190c  jnz     loc_180011A31
0x180011912  mov     rax, [rcx+20h]
0x180011916  cmp     [rax+38h], bl
0x180011919  jz      loc_180011A21
0x18001191f  mov     rax, [rcx+28h]
0x180011923  cmp     [rax+38h], bl
0x180011926  jz      loc_180011A21
0x18001192c  mov     rax, [rcx+18h]
0x180011930  test    rax, rax
0x180011933  jz      short loc_18001193E
0x180011935  cmp     [rax+38h], bl
0x180011938  jz      loc_180011A21
0x18001193e  movzx   eax, word ptr [rcx+94h]
0x180011945  cmp     [rcx+90h], eax
0x18001194b  jnz     loc_180011A4E
0x180011951  mov     rcx, [rcx+8]
0x180011955  mov     rax, [rcx]
0x180011958  lea     r8, [rsp+48h+arg_0]
0x18001195d  lea     rdx, [rsp+48h+var_20]
0x180011962  mov     rax, [rax+58h]
0x180011966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196b  test    eax, eax
0x18001196d  jz      short loc_18001198C
0x18001196f  lea     rcx, [rsp+48h+var_28]
0x180011974  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011979  nop
0x18001197a  xor     al, al
0x18001197c  mov     rbx, [rsp+48h+arg_8]
0x180011981  mov     rsi, [rsp+48h+arg_10]
0x180011986  add     rsp, 40h
0x18001198a  pop     rdi
0x18001198b  retn
0x18001198c  mov     eax, [rsp+48h+arg_0]
0x180011990  cmp     [rdi+94h], ax
0x180011997  jz      loc_180011A6B
0x18001199d  nop     dword ptr [rax]
0x1800119a0  cmp     ebx, eax
0x1800119a2  jnb     short loc_180011A04
0x1800119a4  mov     eax, ebx
0x1800119a6  lea     rsi, ds:0[rax*8]
0x1800119ae  mov     rax, [rsp+48h+var_20]
0x1800119b3  mov     rcx, [rsi+rax]
0x1800119b7  mov     rax, [rcx]
0x1800119ba  mov     rax, [rax+8]
0x1800119be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c3  mov     rcx, [rdi]
0x1800119c6  mov     r8, [rcx+88h]
0x1800119cd  mov     edx, eax
0x1800119cf  mov     rcx, rdi
0x1800119d2  mov     rax, r8
0x1800119d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119da  test    rax, rax
0x1800119dd  jnz     short loc_1800119FC
0x1800119df  mov     rax, [rsp+48h+var_20]
0x1800119e4  mov     rcx, [rsi+rax]
0x1800119e8  mov     rax, [rcx]
0x1800119eb  mov     rax, [rax+20h]
0x1800119ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f4  test    al, 8
0x1800119f6  jz      loc_180011A7D
0x1800119fc  inc     ebx
0x1800119fe  mov     eax, [rsp+48h+arg_0]
0x180011a02  jmp     short loc_1800119A0
0x180011a04  lea     rcx, [rsp+48h+var_28]
0x180011a09  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011a0e  nop
0x180011a0f  mov     al, 1
0x180011a11  mov     rbx, [rsp+48h+arg_8]
0x180011a16  mov     rsi, [rsp+48h+arg_10]
0x180011a1b  add     rsp, 40h
0x180011a1f  pop     rdi
0x180011a20  retn
0x180011a21  lea     rcx, [rsp+48h+var_28]
0x180011a26  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011a2b  nop
0x180011a2c  jmp     loc_18001197A
0x180011a31  lea     rcx, [rsp+48h+var_28]
0x180011a36  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011a3b  nop
0x180011a3c  xor     al, al
0x180011a3e  mov     rbx, [rsp+48h+arg_8]
0x180011a43  mov     rsi, [rsp+48h+arg_10]
0x180011a48  add     rsp, 40h
0x180011a4c  pop     rdi
0x180011a4d  retn
0x180011a4e  lea     rcx, [rsp+48h+var_28]
0x180011a53  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011a58  nop
0x180011a59  xor     al, al
0x180011a5b  mov     rbx, [rsp+48h+arg_8]
0x180011a60  mov     rsi, [rsp+48h+arg_10]
0x180011a65  add     rsp, 40h
0x180011a69  pop     rdi
0x180011a6a  retn
0x180011a6b  lea     rcx, [rsp+48h+var_28]
0x180011a70  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011a75  nop
0x180011a76  mov     al, 1
0x180011a78  jmp     loc_18001197C
0x180011a7d  lea     rcx, [rsp+48h+var_28]
0x180011a82  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011a87  nop
0x180011a88  jmp     loc_18001197A
```
