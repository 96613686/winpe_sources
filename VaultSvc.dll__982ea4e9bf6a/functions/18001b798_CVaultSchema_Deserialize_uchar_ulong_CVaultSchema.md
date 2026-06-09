# CVaultSchema::Deserialize(uchar *,ulong,CVaultSchema * *)

- ea: `0x18001b798`
- end: `0x18001b95c`
- name: `?Deserialize@CVaultSchema@@SAKPEAEKPEAPEAV1@@Z`
- size: `452`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct CVaultSchema **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18001b6b0`

## callees

- `0x180003140`
- `0x18001b798`
- `0x18001b9c0`
- `0x18001bdb4`
- `0x18003b7d8`
- `0x18003be38`

## pseudocode

```c
__int64 __fastcall CVaultSchema::Deserialize(unsigned __int8 *a1, unsigned int a2, struct CVaultSchema **a3)
{
  __int64 v4; // r9
  unsigned int v6; // esi
  int v7; // r10d
  unsigned int v8; // r8d
  unsigned int v9; // edi
  struct CVaultSchema *v10; // rdi
  unsigned int v11; // ebx
  __int128 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 (__fastcall *v14)(__int64); // [rsp+40h] [rbp-20h] BYREF
  CVaultSchema *v15; // [rsp+48h] [rbp-18h] BYREF
  int v16; // [rsp+50h] [rbp-10h]

  v14 = AutoDereference<IVaultKeyManager>;
  v15 = 0;
  v16 = 0;
  if ( a2 < 4 )
    goto LABEL_16;
  v4 = *(unsigned int *)a1;
  if ( (_DWORD)v4 == 1 )
  {
    if ( a2 - 4 >= 0x10 )
    {
      v13 = *(_OWORD *)(a1 + 4);
      if ( a2 - 20 >= 4 )
      {
        v6 = a2 - 24;
        if ( a2 - 24 >= 4 )
        {
          v7 = *((_DWORD *)a1 + 5);
          v8 = *((_DWORD *)a1 + 6);
          if ( (v7 & 1) != 0 || v8 >= 3 )
          {
            v9 = CVaultSchema::CreateNewSchemaInternal(&v13, v7, v8, 1, &v15);
            if ( v9 )
            {
              CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
              return v9;
            }
            else
            {
              v10 = v15;
              v11 = CVaultSchema::DeserializeSchema(v15, a1 + 28, v6 - 4);
              if ( v11 )
              {
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
                return v11;
              }
              else
              {
                v15 = 0;
                *a3 = v10;
                CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
                return 0;
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                WPP_3dd6b994768d37e93a54dacfc95035d2_Traceguids,
                v8,
                v7);
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
            return 1358;
          }
        }
      }
    }
LABEL_16:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return 122;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3dd6b994768d37e93a54dacfc95035d2_Traceguids, v4);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
  return 1630;
}

```

## disassembly

```asm
0x18001b798  push    rbp
0x18001b79a  push    rbx
0x18001b79b  push    rsi
0x18001b79c  push    rdi
0x18001b79d  push    r14
0x18001b79f  mov     rbp, rsp
0x18001b7a2  sub     rsp, 60h
0x18001b7a6  mov     r14, r8
0x18001b7a9  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001b7b0  mov     [rbp+var_20], rax
0x18001b7b4  mov     [rbp+var_18], 0
0x18001b7bc  mov     [rbp+var_10], 0
0x18001b7c3  cmp     edx, 4
0x18001b7c6  jb      loc_18001B8D3
0x18001b7cc  mov     r9d, [rcx]
0x18001b7cf  cmp     r9d, 1
0x18001b7d3  jnz     loc_18001B8E4
0x18001b7d9  lea     eax, [rdx-4]
0x18001b7dc  cmp     eax, 10h
0x18001b7df  jb      loc_18001B950
0x18001b7e5  mov     rbx, rcx
0x18001b7e8  movups  xmm0, xmmword ptr [rcx+4]
0x18001b7ec  movdqu  [rbp+var_30], xmm0
0x18001b7f1  add     eax, 0FFFFFFF0h
0x18001b7f4  cmp     eax, 4
0x18001b7f7  jb      loc_18001B944
0x18001b7fd  lea     esi, [rax-4]
0x18001b800  cmp     esi, 4
0x18001b803  jb      loc_18001B938
0x18001b809  mov     r10d, [rcx+14h]
0x18001b80d  mov     r8d, [rcx+18h]
0x18001b811  test    r9b, r10b
0x18001b814  jz      short loc_18001B885
0x18001b816  lea     rax, [rbp+var_18]
0x18001b81a  mov     [rsp+60h+var_40], rax
0x18001b81f  mov     r9d, 1
0x18001b825  mov     edx, r10d
0x18001b828  lea     rcx, [rbp+var_30]
0x18001b82c  call    ?CreateNewSchemaInternal@CVaultSchema@@SAKPEBU_GUID@@W4efSchemaProperties@@KHPEAPEAV1@@Z; CVaultSchema::CreateNewSchemaInternal(_GUID const *,efSchemaProperties,ulong,int,CVaultSchema * *)
0x18001b831  mov     edi, eax
0x18001b833  test    eax, eax
0x18001b835  jnz     short loc_18001B877
0x18001b837  mov     rdi, [rbp+var_18]
0x18001b83b  lea     r8d, [rsi-4]; unsigned int
0x18001b83f  lea     rdx, [rbx+1Ch]; unsigned __int8 *
0x18001b843  mov     rcx, rdi; this
0x18001b846  call    ?DeserializeSchema@CVaultSchema@@AEAAKPEAEK@Z; CVaultSchema::DeserializeSchema(uchar *,ulong)
0x18001b84b  mov     ebx, eax
0x18001b84d  test    eax, eax
0x18001b84f  jnz     loc_18001B927
0x18001b855  mov     [rbp+var_18], 0
0x18001b85d  mov     [r14], rdi
0x18001b860  lea     rcx, [rbp+var_20]
0x18001b864  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b869  nop
0x18001b86a  xor     eax, eax
0x18001b86c  add     rsp, 60h
0x18001b870  pop     r14
0x18001b872  pop     rdi
0x18001b873  pop     rsi
0x18001b874  pop     rbx
0x18001b875  pop     rbp
0x18001b876  retn
0x18001b877  lea     rcx, [rbp+var_20]
0x18001b87b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b880  nop
0x18001b881  mov     eax, edi
0x18001b883  jmp     short loc_18001B86C
0x18001b885  cmp     r8d, 3
0x18001b889  jnb     short loc_18001B816
0x18001b88b  lea     rax, WPP_GLOBAL_Control
0x18001b892  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b899  cmp     rcx, rax
0x18001b89c  jz      short loc_18001B8C2
0x18001b89e  test    byte ptr [rcx+1Ch], 2
0x18001b8a2  jz      short loc_18001B8C2
0x18001b8a4  mov     edx, 11h
0x18001b8a9  mov     dword ptr [rsp+60h+var_40], r10d
0x18001b8ae  mov     r9d, r8d
0x18001b8b1  lea     r8, WPP_3dd6b994768d37e93a54dacfc95035d2_Traceguids
0x18001b8b8  mov     rcx, [rcx+10h]
0x18001b8bc  call    WPP_SF_dd
0x18001b8c1  nop
0x18001b8c2  lea     rcx, [rbp+var_20]
0x18001b8c6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b8cb  nop
0x18001b8cc  mov     eax, 54Eh
0x18001b8d1  jmp     short loc_18001B86C
0x18001b8d3  lea     rcx, [rbp+var_20]
0x18001b8d7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b8dc  nop
0x18001b8dd  mov     eax, 7Ah ; 'z'
0x18001b8e2  jmp     short loc_18001B86C
0x18001b8e4  lea     rax, WPP_GLOBAL_Control
0x18001b8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8f2  cmp     rcx, rax
0x18001b8f5  jz      short loc_18001B913
0x18001b8f7  test    byte ptr [rcx+1Ch], 2
0x18001b8fb  jz      short loc_18001B913
0x18001b8fd  mov     edx, 10h
0x18001b902  lea     r8, WPP_3dd6b994768d37e93a54dacfc95035d2_Traceguids
0x18001b909  mov     rcx, [rcx+10h]
0x18001b90d  call    WPP_SF_d
0x18001b912  nop
0x18001b913  lea     rcx, [rbp+var_20]
0x18001b917  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b91c  nop
0x18001b91d  mov     eax, 65Eh
0x18001b922  jmp     loc_18001B86C
0x18001b927  lea     rcx, [rbp+var_20]
0x18001b92b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b930  nop
0x18001b931  mov     eax, ebx
0x18001b933  jmp     loc_18001B86C
0x18001b938  lea     rcx, [rbp+var_20]
0x18001b93c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b941  nop
0x18001b942  jmp     short loc_18001B8DD
0x18001b944  lea     rcx, [rbp+var_20]
0x18001b948  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b94d  nop
0x18001b94e  jmp     short loc_18001B8DD
0x18001b950  lea     rcx, [rbp+var_20]
0x18001b954  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001b959  nop
0x18001b95a  jmp     short loc_18001B8DD
```
