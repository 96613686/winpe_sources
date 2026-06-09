# FreeRootKey(_ROOT_KEY_HEADER *)

- ea: `0x180004e20`
- end: `0x180004ed8`
- name: `?FreeRootKey@@YAXPEAU_ROOT_KEY_HEADER@@@Z`
- size: `184`
- prototype: `void __fastcall(struct _ROOT_KEY_HEADER *lpMem)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005740`
- `0x180007d28`
- `0x180008afc`
- `0x180008e1c`
- `0x180009a14`

## callees

- `0x180004e20`
- `0x180004ee0`
- `0x180010950`

## pseudocode

```c
void __fastcall FreeRootKey(struct _ROOT_KEY_HEADER *lpMem)
{
  __int64 v1; // rax
  char *i; // rcx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  _OWORD v13[10]; // [rsp+20h] [rbp-A8h] BYREF

  if ( lpMem )
  {
    v1 = *((unsigned int *)lpMem + 38);
    for ( i = (char *)lpMem + 160; v1; --v1 )
      *i++ = 0;
    v4 = *((_OWORD *)lpMem + 1);
    v13[0] = *(_OWORD *)lpMem;
    v5 = *((_OWORD *)lpMem + 2);
    v13[1] = v4;
    v6 = *((_OWORD *)lpMem + 3);
    v13[2] = v5;
    v7 = *((_OWORD *)lpMem + 4);
    v13[3] = v6;
    v8 = *((_OWORD *)lpMem + 5);
    v13[4] = v7;
    v9 = *((_OWORD *)lpMem + 6);
    v13[5] = v8;
    v10 = *((_OWORD *)lpMem + 7);
    v13[6] = v9;
    v11 = *((_OWORD *)lpMem + 8);
    v13[7] = v10;
    v12 = *((_OWORD *)lpMem + 9);
    v13[8] = v11;
    v13[9] = v12;
    FreeRootKeyConfig(v13);
    SIDKeyProvFree(lpMem);
  }
}

```

## disassembly

```asm
0x180004e20  test    rcx, rcx
0x180004e23  jz      locret_180004ED7
0x180004e29  push    rbx
0x180004e2a  sub     rsp, 0C0h
0x180004e31  mov     eax, [rcx+98h]
0x180004e37  mov     rbx, rcx
0x180004e3a  add     rcx, 0A0h
0x180004e41  test    rax, rax
0x180004e44  jz      short loc_180004E52
0x180004e46  mov     byte ptr [rcx], 0
0x180004e49  inc     rcx
0x180004e4c  sub     rax, 1
0x180004e50  jnz     short loc_180004E46
0x180004e52  movups  xmm0, xmmword ptr [rbx]
0x180004e55  lea     rcx, [rsp+0C8h+var_A8]
0x180004e5a  movups  xmm1, xmmword ptr [rbx+10h]
0x180004e5e  movups  [rsp+0C8h+var_A8], xmm0
0x180004e63  movups  xmm0, xmmword ptr [rbx+20h]
0x180004e67  movups  [rsp+0C8h+var_98], xmm1
0x180004e6c  movups  xmm1, xmmword ptr [rbx+30h]
0x180004e70  movups  [rsp+0C8h+var_88], xmm0
0x180004e75  movups  xmm0, xmmword ptr [rbx+40h]
0x180004e79  movups  [rsp+0C8h+var_78], xmm1
0x180004e7e  movups  xmm1, xmmword ptr [rbx+50h]
0x180004e82  movups  [rsp+0C8h+var_68], xmm0
0x180004e87  movups  xmm0, xmmword ptr [rbx+60h]
0x180004e8b  movups  [rsp+0C8h+var_58], xmm1
0x180004e90  movups  xmm1, xmmword ptr [rbx+70h]
0x180004e94  movups  [rsp+0C8h+var_48], xmm0
0x180004e9c  movups  xmm0, xmmword ptr [rbx+80h]
0x180004ea3  movups  [rsp+0C8h+var_38], xmm1
0x180004eab  movups  xmm1, xmmword ptr [rbx+90h]
0x180004eb2  movups  [rsp+0C8h+var_28], xmm0
0x180004eba  movups  [rsp+0C8h+var_18], xmm1
0x180004ec2  call    ?FreeRootKeyConfig@@YAXU_ROOT_KEY_HEADER@@@Z; FreeRootKeyConfig(_ROOT_KEY_HEADER)
0x180004ec7  mov     rcx, rbx; lpMem
0x180004eca  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004ecf  add     rsp, 0C0h
0x180004ed6  pop     rbx
0x180004ed7  retn
```
