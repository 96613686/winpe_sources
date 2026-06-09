# SSPI_APP_CONTEXT::AdjustFlagsForCbt(IHttpContext *,ulong *,_SecBuffer *,int *)

- ea: `0x1800066cc`
- end: `0x180006803`
- name: `?AdjustFlagsForCbt@SSPI_APP_CONTEXT@@QEAAJPEAVIHttpContext@@PEAKPEAU_SecBuffer@@PEAH@Z`
- size: `311`
- prototype: `__int64 __fastcall(SSPI_APP_CONTEXT *__hidden this, struct IHttpContext *, unsigned int *, struct _SecBuffer *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021f0`
- `0x1800048f0`

## callees

- `0x1800066cc`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall SSPI_APP_CONTEXT::AdjustFlagsForCbt(
        SSPI_APP_CONTEXT *this,
        struct IHttpContext *a2,
        unsigned int *a3,
        struct _SecBuffer *a4,
        int *a5)
{
  bool v5; // zf
  __int64 v9; // r14
  __int64 result; // rax
  void *v11; // rdx
  unsigned int v12; // ecx
  _BYTE *v13; // rax
  int *v14; // rax
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  void *v17; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+20h] BYREF

  v5 = *((_DWORD *)this + 20) == 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  if ( v5 )
    return 0;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v15 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(*(_QWORD *)s_pGlobalInfo + 200LL))(
             s_pGlobalInfo,
             0,
             &v15);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, __int64 *))(*(_QWORD *)v15 + 224LL))(
               v15,
               &GUID_e8698f7e_576e_4cac_a309_67435355faef,
               v9,
               &GUID_d9244ae1_51f8_4aa1_a66d_19277c33e610,
               &v16);
    if ( (int)result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(__int64, void **, unsigned int *))(*(_QWORD *)v16 + 192LL))(v16, &v17, &v18);
      if ( (int)result >= 0 )
      {
        v11 = v17;
        v12 = v18;
        if ( v17 && v18 )
        {
          v13 = (char *)this + 84;
          goto LABEL_9;
        }
        v13 = (char *)this + 84;
        if ( (*((_BYTE *)this + 84) & 1) != 0 )
        {
LABEL_9:
          if ( (*v13 & 0x20) == 0 )
          {
            if ( *((_DWORD *)this + 20) == 1 )
              *a3 |= 0x10000000u;
            if ( (*v13 & 1) != 0 )
            {
              *a3 |= 0x4000000u;
            }
            else
            {
              v14 = a5;
              a4->BufferType = 14;
              a4->pvBuffer = v11;
              a4->cbBuffer = v12;
              *v14 = 1;
            }
          }
        }
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800066cc  mov     [rsp-18h+arg_8], rbx
0x1800066d1  mov     [rsp-18h+arg_10], rsi
0x1800066d6  push    rbp
0x1800066d7  push    rdi
0x1800066d8  push    r14
0x1800066da  mov     rbp, rsp
0x1800066dd  sub     rsp, 50h
0x1800066e1  cmp     dword ptr [rcx+50h], 0
0x1800066e5  mov     rsi, r9
0x1800066e8  mov     rbx, r8
0x1800066eb  mov     [rbp+var_10], 0
0x1800066f3  mov     rdi, rcx
0x1800066f6  mov     [rbp+arg_0], 0
0x1800066fd  mov     [rbp+var_18], 0
0x180006705  jz      loc_1800067EC
0x18000670b  mov     rax, [rdx]
0x18000670e  mov     rcx, rdx
0x180006711  mov     rax, [rax+18h]
0x180006715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671a  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180006721  lea     r8, [rbp+var_20]
0x180006725  mov     r14, rax
0x180006728  mov     [rbp+var_20], 0
0x180006730  mov     rdx, [rcx]
0x180006733  mov     rax, [rdx+0C8h]
0x18000673a  xor     edx, edx
0x18000673c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006741  test    eax, eax
0x180006743  js      loc_1800067EE
0x180006749  mov     rcx, [rbp+var_20]
0x18000674d  lea     rdx, [rbp+var_18]
0x180006751  mov     [rsp+50h+var_30], rdx
0x180006756  lea     r9, _GUID_d9244ae1_51f8_4aa1_a66d_19277c33e610
0x18000675d  mov     r8, r14
0x180006760  lea     rdx, _GUID_e8698f7e_576e_4cac_a309_67435355faef
0x180006767  mov     rax, [rcx]
0x18000676a  mov     rax, [rax+0E0h]
0x180006771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006776  test    eax, eax
0x180006778  js      short loc_1800067EE
0x18000677a  mov     rcx, [rbp+var_18]
0x18000677e  lea     r8, [rbp+arg_0]
0x180006782  lea     rdx, [rbp+var_10]
0x180006786  mov     rax, [rcx]
0x180006789  mov     rax, [rax+0C0h]
0x180006790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006795  test    eax, eax
0x180006797  js      short loc_1800067EE
0x180006799  mov     rdx, [rbp+var_10]
0x18000679d  mov     r8d, 1
0x1800067a3  mov     ecx, [rbp+arg_0]
0x1800067a6  test    rdx, rdx
0x1800067a9  jz      short loc_1800067B5
0x1800067ab  test    ecx, ecx
0x1800067ad  jz      short loc_1800067B5
0x1800067af  lea     rax, [rdi+54h]
0x1800067b3  jmp     short loc_1800067BE
0x1800067b5  lea     rax, [rdi+54h]
0x1800067b9  test    [rax], r8b
0x1800067bc  jz      short loc_1800067EC
0x1800067be  test    byte ptr [rax], 20h
0x1800067c1  jnz     short loc_1800067EC
0x1800067c3  cmp     [rdi+50h], r8d
0x1800067c7  jnz     short loc_1800067CD
0x1800067c9  bts     dword ptr [rbx], 1Ch
0x1800067cd  test    [rax], r8b
0x1800067d0  jz      short loc_1800067D8
0x1800067d2  bts     dword ptr [rbx], 1Ah
0x1800067d6  jmp     short loc_1800067EC
0x1800067d8  mov     rax, [rbp+arg_20]
0x1800067dc  mov     dword ptr [rsi+4], 0Eh
0x1800067e3  mov     [rsi+8], rdx
0x1800067e7  mov     [rsi], ecx
0x1800067e9  mov     [rax], r8d
0x1800067ec  xor     eax, eax
0x1800067ee  lea     r11, [rsp+50h+var_s0]
0x1800067f3  mov     rbx, [r11+28h]
0x1800067f7  mov     rsi, [r11+30h]
0x1800067fb  mov     rsp, r11
0x1800067fe  pop     r14
0x180006800  pop     rdi
0x180006801  pop     rbp
0x180006802  retn
```
