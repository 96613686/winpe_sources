# FreeL0Key(_L0_key *)

- ea: `0x180004d5c`
- end: `0x180004e15`
- name: `?FreeL0Key@@YAXPEAU_L0_key@@@Z`
- size: `185`
- prototype: `void __fastcall(struct _L0_key *lpMem)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004624`
- `0x180007d28`
- `0x18000898c`
- `0x180008afc`
- `0x180008cf0`
- `0x180008eb4`
- `0x180009a14`

## callees

- `0x180004d5c`
- `0x180004ee0`
- `0x180010950`

## pseudocode

```c
void __fastcall FreeL0Key(struct _L0_key *lpMem)
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
    v1 = *((unsigned int *)lpMem + 40);
    for ( i = (char *)lpMem + 176; v1; --v1 )
      *i++ = 0;
    v4 = *(_OWORD *)((char *)lpMem + 24);
    v13[0] = *(_OWORD *)((char *)lpMem + 8);
    v5 = *(_OWORD *)((char *)lpMem + 40);
    v13[1] = v4;
    v6 = *(_OWORD *)((char *)lpMem + 56);
    v13[2] = v5;
    v7 = *(_OWORD *)((char *)lpMem + 72);
    v13[3] = v6;
    v8 = *(_OWORD *)((char *)lpMem + 88);
    v13[4] = v7;
    v9 = *(_OWORD *)((char *)lpMem + 104);
    v13[5] = v8;
    v10 = *(_OWORD *)((char *)lpMem + 120);
    v13[6] = v9;
    v11 = *(_OWORD *)((char *)lpMem + 136);
    v13[7] = v10;
    v12 = *(_OWORD *)((char *)lpMem + 152);
    v13[8] = v11;
    v13[9] = v12;
    FreeRootKeyConfig(v13);
    SIDKeyProvFree(lpMem);
  }
}

```

## disassembly

```asm
0x180004d5c  test    rcx, rcx
0x180004d5f  jz      locret_180004E14
0x180004d65  push    rbx
0x180004d66  sub     rsp, 0C0h
0x180004d6d  mov     eax, [rcx+0A0h]
0x180004d73  mov     rbx, rcx
0x180004d76  add     rcx, 0B0h
0x180004d7d  test    rax, rax
0x180004d80  jz      short loc_180004D8E
0x180004d82  mov     byte ptr [rcx], 0
0x180004d85  inc     rcx
0x180004d88  sub     rax, 1
0x180004d8c  jnz     short loc_180004D82
0x180004d8e  movups  xmm0, xmmword ptr [rbx+8]
0x180004d92  lea     rcx, [rsp+0C8h+var_A8]
0x180004d97  movups  xmm1, xmmword ptr [rbx+18h]
0x180004d9b  movups  [rsp+0C8h+var_A8], xmm0
0x180004da0  movups  xmm0, xmmword ptr [rbx+28h]
0x180004da4  movups  [rsp+0C8h+var_98], xmm1
0x180004da9  movups  xmm1, xmmword ptr [rbx+38h]
0x180004dad  movups  [rsp+0C8h+var_88], xmm0
0x180004db2  movups  xmm0, xmmword ptr [rbx+48h]
0x180004db6  movups  [rsp+0C8h+var_78], xmm1
0x180004dbb  movups  xmm1, xmmword ptr [rbx+58h]
0x180004dbf  movups  [rsp+0C8h+var_68], xmm0
0x180004dc4  movups  xmm0, xmmword ptr [rbx+68h]
0x180004dc8  movups  [rsp+0C8h+var_58], xmm1
0x180004dcd  movups  xmm1, xmmword ptr [rbx+78h]
0x180004dd1  movups  [rsp+0C8h+var_48], xmm0
0x180004dd9  movups  xmm0, xmmword ptr [rbx+88h]
0x180004de0  movups  [rsp+0C8h+var_38], xmm1
0x180004de8  movups  xmm1, xmmword ptr [rbx+98h]
0x180004def  movups  [rsp+0C8h+var_28], xmm0
0x180004df7  movups  [rsp+0C8h+var_18], xmm1
0x180004dff  call    ?FreeRootKeyConfig@@YAXU_ROOT_KEY_HEADER@@@Z; FreeRootKeyConfig(_ROOT_KEY_HEADER)
0x180004e04  mov     rcx, rbx; lpMem
0x180004e07  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004e0c  add     rsp, 0C0h
0x180004e13  pop     rbx
0x180004e14  retn
```
