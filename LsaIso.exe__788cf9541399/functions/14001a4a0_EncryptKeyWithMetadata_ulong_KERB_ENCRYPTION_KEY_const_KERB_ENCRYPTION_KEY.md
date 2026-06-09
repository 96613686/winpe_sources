# EncryptKeyWithMetadata(ulong,_KERB_ENCRYPTION_KEY const *,_KERB_ENCRYPTION_KEY *)

- ea: `0x14001a4a0`
- end: `0x14001a613`
- name: `?EncryptKeyWithMetadata@@YAJKPEBU_KERB_ENCRYPTION_KEY@@PEAU1@@Z`
- size: `371`
- prototype: `__int64 __fastcall(unsigned int, const struct _KERB_ENCRYPTION_KEY *, struct _KERB_ENCRYPTION_KEY *)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140014560`
- `0x1400164a0`
- `0x1400170e0`
- `0x140019210`
- `0x14001a170`
- `0x14001a1c0`
- `0x14001a210`
- `0x14001a260`
- `0x14001a620`

## callees

- `0x140003ad6`
- `0x14001a4a0`
- `0x1400371bc`
- `0x14003a010`

## import_xrefs

- `KerbClientShared!KerbClientAlloc` at `0x14001a50d`
- `KerbClientShared!KerbClientAlloc` at `0x14001a50d`
- `KerbClientShared!KerbClientAlloc` at `0x14001a566`
- `KerbClientShared!KerbClientFree` at `0x14001a5f6`
- `KerbClientShared!KerbClientFree` at `0x14001a581`
- `KerbClientShared!KerbClientFree` at `0x14001a5f6`

## pseudocode

```c
__int64 __fastcall EncryptKeyWithMetadata(
        int a1,
        const struct _KERB_ENCRYPTION_KEY *a2,
        struct _KERB_ENCRYPTION_KEY *a3)
{
  __int64 result; // rax
  unsigned int v7; // eax
  unsigned int v8; // r14d
  __int64 v9; // rbp
  _DWORD *v10; // rax
  _BYTE *v11; // rdi
  int v12; // r14d
  _BYTE *i; // rcx
  int v14; // [rsp+88h] [rbp+10h] BYREF

  if ( !a2 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225712LL;
  v7 = *((_DWORD *)a2 + 4);
  if ( v7 )
  {
    v8 = v7 + 16;
    if ( v7 + 16 >= v7 )
    {
      v9 = v8;
      v10 = KerbClientAlloc(v8);
      v11 = v10;
      if ( v10 )
      {
        v10[2] = a1;
        v10[3] = *((_DWORD *)a2 + 4);
        v10[1] = *((_DWORD *)a2 + 3);
        *v10 = 1;
        memcpy_0(v10 + 4, *((const void **)a2 + 3), *((unsigned int *)a2 + 4));
        if ( *((_DWORD *)a2 + 2) != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v14 = 0;
        v12 = (*(__int64 (__fastcall **)(const char *, _BYTE *, _QWORD, void *(*const)(unsigned __int64), void (*const)(void *), int, char *, int *))LsaIsoFunctions)(
                "KerberosKeyWithMetadata",
                v11,
                v8,
                KerbClientAlloc,
                KerbClientFree,
                1,
                (char *)a3 + 24,
                &v14);
        *((_DWORD *)a3 + 4) = v14;
        if ( v12 < 0 )
        {
          *(_OWORD *)a3 = 0;
          *((_OWORD *)a3 + 1) = 0;
          *((_QWORD *)a3 + 4) = 0;
        }
        else
        {
          *((_DWORD *)a3 + 3) = *((_DWORD *)a2 + 3);
          *((_DWORD *)a3 + 2) = 3;
        }
        for ( i = v11; v9; --v9 )
          *i++ = 0;
        KerbClientFree(v11);
        return (unsigned int)v12;
      }
      else
      {
        return 3221225626LL;
      }
    }
    else
    {
      return 3221225621LL;
    }
  }
  else
  {
    *((_DWORD *)a3 + 3) = *((_DWORD *)a2 + 3);
    result = 0;
    *((_DWORD *)a3 + 2) = 3;
  }
  return result;
}

```

## disassembly

```asm
0x14001a4a0  mov     [rsp+arg_0], rbx
0x14001a4a5  push    rbp
0x14001a4a6  push    rsi
0x14001a4a7  push    rdi
0x14001a4a8  push    r14
0x14001a4aa  push    r15
0x14001a4ac  sub     rsp, 50h
0x14001a4b0  mov     rbx, r8
0x14001a4b3  mov     rsi, rdx
0x14001a4b6  mov     r15d, ecx
0x14001a4b9  test    rdx, rdx
0x14001a4bc  jnz     short loc_14001A4C8
0x14001a4be  mov     eax, 0C00000EFh
0x14001a4c3  jmp     loc_14001A5FF
0x14001a4c8  test    rbx, rbx
0x14001a4cb  jnz     short loc_14001A4D7
0x14001a4cd  mov     eax, 0C00000F0h
0x14001a4d2  jmp     loc_14001A5FF
0x14001a4d7  mov     eax, [rdx+10h]
0x14001a4da  test    eax, eax
0x14001a4dc  jnz     short loc_14001A4F4
0x14001a4de  mov     eax, [rdx+0Ch]
0x14001a4e1  mov     [r8+0Ch], eax
0x14001a4e5  xor     eax, eax
0x14001a4e7  mov     dword ptr [r8+8], 3
0x14001a4ef  jmp     loc_14001A5FF
0x14001a4f4  lea     r14d, [rax+10h]
0x14001a4f8  cmp     r14d, eax
0x14001a4fb  jnb     short loc_14001A507
0x14001a4fd  mov     eax, 0C0000095h
0x14001a502  jmp     loc_14001A5FF
0x14001a507  mov     ecx, r14d
0x14001a50a  mov     ebp, r14d
0x14001a50d  call    cs:__imp_?KerbClientAlloc@@YAPEAX_K@Z; KerbClientAlloc(unsigned __int64)
0x14001a513  mov     rdi, rax
0x14001a516  test    rax, rax
0x14001a519  jnz     short loc_14001A525
0x14001a51b  mov     eax, 0C000009Ah
0x14001a520  jmp     loc_14001A5FF
0x14001a525  mov     [rax+8], r15d
0x14001a529  lea     rcx, [rdi+10h]; void *
0x14001a52d  mov     eax, [rsi+10h]
0x14001a530  mov     [rdi+0Ch], eax
0x14001a533  mov     eax, [rsi+0Ch]
0x14001a536  mov     [rdi+4], eax
0x14001a539  mov     dword ptr [rdi], 1
0x14001a53f  mov     r8d, [rsi+10h]; Size
0x14001a543  mov     rdx, [rsi+18h]; Src
0x14001a547  call    memcpy_0
0x14001a54c  cmp     dword ptr [rsi+8], 1
0x14001a550  jz      short loc_14001A557
0x14001a552  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001a557  mov     rax, cs:?LsaIsoFunctions@@3PEBU_LsaIsoSupportFunctions@@EB; _LsaIsoSupportFunctions const * const LsaIsoFunctions
0x14001a55e  lea     rdx, [rsp+78h+arg_8]
0x14001a566  mov     r9, cs:__imp_?KerbClientAlloc@@YAPEAX_K@Z; KerbClientAlloc(unsigned __int64)
0x14001a56d  lea     rcx, [rbx+18h]
0x14001a571  mov     [rsp+78h+var_40], rdx
0x14001a576  mov     r8d, r14d
0x14001a579  mov     [rsp+78h+var_48], rcx
0x14001a57e  mov     rdx, rdi
0x14001a581  mov     rcx, cs:__imp_?KerbClientFree@@YAXPEAX@Z; KerbClientFree(void *)
0x14001a588  mov     [rsp+78h+arg_8], 0
0x14001a593  mov     rax, [rax]
0x14001a596  mov     [rsp+78h+var_50], 1
0x14001a59e  mov     [rsp+78h+var_58], rcx
0x14001a5a3  lea     rcx, aKerberoskeywit; "KerberosKeyWithMetadata"
0x14001a5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5af  mov     ecx, [rsp+78h+arg_8]
0x14001a5b6  mov     r14d, eax
0x14001a5b9  mov     [rbx+10h], ecx
0x14001a5bc  test    eax, eax
0x14001a5be  js      short loc_14001A5CF
0x14001a5c0  mov     ecx, [rsi+0Ch]
0x14001a5c3  mov     [rbx+0Ch], ecx
0x14001a5c6  mov     dword ptr [rbx+8], 3
0x14001a5cd  jmp     short loc_14001A5DF
0x14001a5cf  xorps   xmm0, xmm0
0x14001a5d2  xor     eax, eax
0x14001a5d4  movups  xmmword ptr [rbx], xmm0
0x14001a5d7  movups  xmmword ptr [rbx+10h], xmm0
0x14001a5db  mov     [rbx+20h], rax
0x14001a5df  mov     rcx, rdi
0x14001a5e2  test    rbp, rbp
0x14001a5e5  jz      short loc_14001A5F3
0x14001a5e7  mov     byte ptr [rcx], 0
0x14001a5ea  inc     rcx
0x14001a5ed  sub     rbp, 1
0x14001a5f1  jnz     short loc_14001A5E7
0x14001a5f3  mov     rcx, rdi
0x14001a5f6  call    cs:__imp_?KerbClientFree@@YAXPEAX@Z; KerbClientFree(void *)
0x14001a5fc  mov     eax, r14d
0x14001a5ff  mov     rbx, [rsp+78h+arg_0]
0x14001a607  add     rsp, 50h
0x14001a60b  pop     r15
0x14001a60d  pop     r14
0x14001a60f  pop     rdi
0x14001a610  pop     rsi
0x14001a611  pop     rbp
0x14001a612  retn
```
