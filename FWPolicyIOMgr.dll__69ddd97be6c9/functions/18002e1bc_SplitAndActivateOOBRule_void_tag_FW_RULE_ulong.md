# SplitAndActivateOOBRule(void *,_tag_FW_RULE *,ulong)

- ea: `0x18002e1bc`
- end: `0x18002e454`
- name: `?SplitAndActivateOOBRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z`
- size: `664`
- prototype: `__int64 __fastcall(struct _tag_WF_POLICY_STORE *, struct _tag_FW_RULE *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b030`

## callees

- `0x1800042c4`
- `0x180004320`
- `0x1800049e0`
- `0x18001f650`
- `0x18001ffd4`
- `0x18002e1bc`
- `0x180031008`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002e305`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002e305`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e35c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e35c`
- `fwbase!FwFree` at `0x18002e3f1`
- `fwbase!FwFree` at `0x18002e3f1`
- `fwbase!FwStringCopy` at `0x18002e406`
- `fwbase!FwStringCopy` at `0x18002e406`

## pseudocode

```c
__int64 __fastcall SplitAndActivateOOBRule(struct _tag_WF_POLICY_STORE *a1, struct _tag_FW_RULE *a2, int a3)
{
  int v6; // edi
  _OWORD *v7; // rcx
  __int64 v8; // rdx
  struct _tag_FW_RULE *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v23; // rax
  int v24; // eax
  HRESULT v25; // eax
  unsigned int v26; // ebx
  LPCOLESTR v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  int v30; // edi
  int v31; // eax
  OLECHAR *v32; // rcx
  _BYTE v34[16]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  int v37; // [rsp+58h] [rbp-A8h]
  __int16 v38; // [rsp+154h] [rbp+54h]
  GUID pguid; // [rsp+230h] [rbp+130h] BYREF
  OLECHAR sz[256]; // [rsp+240h] [rbp+140h] BYREF

  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  v6 = *((_DWORD *)a2 + 10);
  v7 = v34;
  v8 = 3;
  v9 = a2;
  do
  {
    v10 = *((_OWORD *)v9 + 1);
    *v7 = *(_OWORD *)v9;
    v11 = *((_OWORD *)v9 + 2);
    v7[1] = v10;
    v12 = *((_OWORD *)v9 + 3);
    v7[2] = v11;
    v13 = *((_OWORD *)v9 + 4);
    v7[3] = v12;
    v14 = *((_OWORD *)v9 + 5);
    v7[4] = v13;
    v15 = *((_OWORD *)v9 + 6);
    v7[5] = v14;
    v16 = *((_OWORD *)v9 + 7);
    v9 = (struct _tag_FW_RULE *)((char *)v9 + 128);
    v7[6] = v15;
    v7[7] = v16;
    v7 += 8;
    --v8;
  }
  while ( v8 );
  v17 = *((_OWORD *)v9 + 1);
  *v7 = *(_OWORD *)v9;
  v18 = *((_OWORD *)v9 + 2);
  v7[1] = v17;
  v19 = *((_OWORD *)v9 + 3);
  v7[2] = v18;
  v20 = *((_OWORD *)v9 + 4);
  v7[3] = v19;
  v21 = *((_OWORD *)v9 + 5);
  v7[4] = v20;
  v22 = *((_OWORD *)v9 + 6);
  v23 = *((_QWORD *)v9 + 14);
  v7[5] = v21;
  v7[6] = v22;
  *((_QWORD *)v7 + 14) = v23;
  v37 = ~(_BYTE)a3 & 7 & (unsigned __int8)v37;
  v24 = FwSetRule(a1, 0, (__int64)v34);
  if ( v24 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      350,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      v36,
      v24);
  v25 = CoCreateGuid(&pguid);
  v26 = v25;
  if ( v25 >= 0 )
  {
    if ( StringFromGUID2(&pguid, sz, 256) )
    {
      v38 |= 1u;
      v30 = a3 & v6;
      v35 = sz;
      v37 = v30;
      v31 = FwAddRule(a1);
      if ( v31 < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          353,
          (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
          v36,
          v31);
      FwFree(*((_QWORD *)a2 + 2));
      v32 = v35;
      *((_QWORD *)a2 + 2) = 0;
      v25 = FwStringCopy(v32, (char *)a2 + 16);
      v26 = v25;
      if ( v25 >= 0 )
      {
        *((_DWORD *)a2 + 10) = v30;
        return v26;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v28 = 354;
        goto LABEL_11;
      }
    }
    else
    {
      v26 = -2147024774;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v28 = 352;
        v29 = 2147942522LL;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v28 = 351;
LABEL_11:
      v29 = (unsigned int)v25;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v29);
    }
  }
  return v26;
}

```

## disassembly

```asm
0x18002e1bc  push    rbp
0x18002e1be  push    rbx
0x18002e1bf  push    rsi
0x18002e1c0  push    rdi
0x18002e1c1  push    r13
0x18002e1c3  push    r14
0x18002e1c5  push    r15
0x18002e1c7  lea     rbp, [rsp-350h]
0x18002e1cf  sub     rsp, 450h
0x18002e1d6  mov     rax, cs:__security_cookie
0x18002e1dd  xor     rax, rsp
0x18002e1e0  mov     [rbp+380h+var_40], rax
0x18002e1e7  mov     r15d, r8d
0x18002e1ea  mov     rsi, rdx
0x18002e1ed  mov     r14, rcx
0x18002e1f0  xorps   xmm0, xmm0
0x18002e1f3  xor     edx, edx; Val
0x18002e1f5  lea     rcx, [rbp+380h+sz]; void *
0x18002e1fc  mov     r8d, 200h; Size
0x18002e202  movups  xmmword ptr [rbp+380h+pguid.Data1], xmm0
0x18002e209  call    memset_0
0x18002e20e  mov     edi, [rsi+28h]
0x18002e211  lea     rcx, [rsp+480h+var_450]
0x18002e216  mov     edx, 3
0x18002e21b  mov     rax, rsi
0x18002e21e  lea     r8d, [rdx+7Dh]
0x18002e222  movups  xmm0, xmmword ptr [rax]
0x18002e225  movups  xmm1, xmmword ptr [rax+10h]
0x18002e229  movups  xmmword ptr [rcx], xmm0
0x18002e22c  movups  xmm0, xmmword ptr [rax+20h]
0x18002e230  movups  xmmword ptr [rcx+10h], xmm1
0x18002e234  movups  xmm1, xmmword ptr [rax+30h]
0x18002e238  movups  xmmword ptr [rcx+20h], xmm0
0x18002e23c  movups  xmm0, xmmword ptr [rax+40h]
0x18002e240  movups  xmmword ptr [rcx+30h], xmm1
0x18002e244  movups  xmm1, xmmword ptr [rax+50h]
0x18002e248  movups  xmmword ptr [rcx+40h], xmm0
0x18002e24c  movups  xmm0, xmmword ptr [rax+60h]
0x18002e250  movups  xmmword ptr [rcx+50h], xmm1
0x18002e254  movups  xmm1, xmmword ptr [rax+70h]
0x18002e258  add     rax, r8
0x18002e25b  movups  xmmword ptr [rcx+60h], xmm0
0x18002e25f  movups  xmmword ptr [rcx+70h], xmm1
0x18002e263  add     rcx, r8
0x18002e266  sub     rdx, 1
0x18002e26a  jnz     short loc_18002E222
0x18002e26c  movups  xmm0, xmmword ptr [rax]
0x18002e26f  lea     r8, [rsp+480h+var_450]
0x18002e274  movups  xmm1, xmmword ptr [rax+10h]
0x18002e278  movups  xmmword ptr [rcx], xmm0
0x18002e27b  movups  xmm0, xmmword ptr [rax+20h]
0x18002e27f  movups  xmmword ptr [rcx+10h], xmm1
0x18002e283  movups  xmm1, xmmword ptr [rax+30h]
0x18002e287  movups  xmmword ptr [rcx+20h], xmm0
0x18002e28b  movups  xmm0, xmmword ptr [rax+40h]
0x18002e28f  movups  xmmword ptr [rcx+30h], xmm1
0x18002e293  movups  xmm1, xmmword ptr [rax+50h]
0x18002e297  movups  xmmword ptr [rcx+40h], xmm0
0x18002e29b  movups  xmm0, xmmword ptr [rax+60h]
0x18002e29f  mov     rax, [rax+70h]
0x18002e2a3  movups  xmmword ptr [rcx+50h], xmm1
0x18002e2a7  movups  xmmword ptr [rcx+60h], xmm0
0x18002e2ab  mov     [rcx+70h], rax
0x18002e2af  mov     eax, r15d
0x18002e2b2  not     eax
0x18002e2b4  mov     rcx, r14; struct _tag_WF_POLICY_STORE *
0x18002e2b7  and     eax, 7
0x18002e2ba  and     [rsp+480h+var_428], eax
0x18002e2be  call    FwSetRule
0x18002e2c3  lea     r13, WPP_GLOBAL_Control
0x18002e2ca  test    eax, eax
0x18002e2cc  jns     short loc_18002E2FE
0x18002e2ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2d5  cmp     rcx, r13
0x18002e2d8  jz      short loc_18002E2FE
0x18002e2da  test    byte ptr [rcx+1Ch], 1
0x18002e2de  jz      short loc_18002E2FE
0x18002e2e0  mov     r9, [rsp+480h+var_438]
0x18002e2e5  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002e2ec  mov     rcx, [rcx+10h]
0x18002e2f0  mov     edx, 15Eh
0x18002e2f5  mov     [rsp+480h+var_460], eax
0x18002e2f9  call    WPP_SF_Sd
0x18002e2fe  lea     rcx, [rbp+380h+pguid]; pguid
0x18002e305  call    cs:__imp_CoCreateGuid
0x18002e30b  mov     ebx, eax
0x18002e30d  test    eax, eax
0x18002e30f  jns     short loc_18002E348
0x18002e311  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e318  cmp     rcx, r13
0x18002e31b  jz      loc_18002E431
0x18002e321  test    byte ptr [rcx+1Ch], 1
0x18002e325  jz      loc_18002E431
0x18002e32b  mov     edx, 15Fh
0x18002e330  mov     r9d, eax
0x18002e333  mov     rcx, [rcx+10h]
0x18002e337  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002e33e  call    WPP_SF_d
0x18002e343  jmp     loc_18002E431
0x18002e348  mov     r8d, 100h; cchMax
0x18002e34e  lea     rdx, [rbp+380h+sz]; lpsz
0x18002e355  lea     rcx, [rbp+380h+pguid]; rguid
0x18002e35c  call    cs:__imp_StringFromGUID2
0x18002e362  test    eax, eax
0x18002e364  jnz     short loc_18002E38F
0x18002e366  mov     ebx, 8007007Ah
0x18002e36b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e372  cmp     rcx, r13
0x18002e375  jz      loc_18002E431
0x18002e37b  test    byte ptr [rcx+1Ch], 1
0x18002e37f  jz      loc_18002E431
0x18002e385  mov     edx, 160h
0x18002e38a  mov     r9d, ebx
0x18002e38d  jmp     short loc_18002E333
0x18002e38f  or      [rbp+380h+var_32C], 1
0x18002e394  lea     rax, [rbp+380h+sz]
0x18002e39b  and     edi, r15d
0x18002e39e  mov     [rsp+480h+var_440], rax
0x18002e3a3  lea     r8, [rsp+480h+var_450]
0x18002e3a8  mov     [rsp+480h+var_428], edi
0x18002e3ac  xor     edx, edx
0x18002e3ae  mov     rcx, r14; struct _tag_WF_POLICY_STORE *
0x18002e3b1  call    FwAddRule
0x18002e3b6  test    eax, eax
0x18002e3b8  jns     short loc_18002E3EA
0x18002e3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3c1  cmp     rcx, r13
0x18002e3c4  jz      short loc_18002E3EA
0x18002e3c6  test    byte ptr [rcx+1Ch], 1
0x18002e3ca  jz      short loc_18002E3EA
0x18002e3cc  mov     r9, [rsp+480h+var_438]
0x18002e3d1  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002e3d8  mov     rcx, [rcx+10h]
0x18002e3dc  mov     edx, 161h
0x18002e3e1  mov     [rsp+480h+var_460], eax
0x18002e3e5  call    WPP_SF_Sd
0x18002e3ea  lea     rbx, [rsi+10h]
0x18002e3ee  mov     rcx, [rbx]
0x18002e3f1  call    cs:__imp_FwFree
0x18002e3f7  mov     rcx, [rsp+480h+var_440]
0x18002e3fc  mov     rdx, rbx
0x18002e3ff  mov     qword ptr [rbx], 0
0x18002e406  call    cs:__imp_FwStringCopy
0x18002e40c  mov     ebx, eax
0x18002e40e  test    eax, eax
0x18002e410  jns     short loc_18002E42E
0x18002e412  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e419  cmp     rcx, r13
0x18002e41c  jz      short loc_18002E431
0x18002e41e  test    byte ptr [rcx+1Ch], 1
0x18002e422  jz      short loc_18002E431
0x18002e424  mov     edx, 162h
0x18002e429  jmp     loc_18002E330
0x18002e42e  mov     [rsi+28h], edi
0x18002e431  mov     eax, ebx
0x18002e433  mov     rcx, [rbp+380h+var_40]
0x18002e43a  xor     rcx, rsp; StackCookie
0x18002e43d  call    __security_check_cookie
0x18002e442  add     rsp, 450h
0x18002e449  pop     r15
0x18002e44b  pop     r14
0x18002e44d  pop     r13
0x18002e44f  pop     rdi
0x18002e450  pop     rsi
0x18002e451  pop     rbx
0x18002e452  pop     rbp
0x18002e453  retn
```
