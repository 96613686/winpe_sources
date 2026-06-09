# BthServOpen

- ea: `0x1800128b0`
- end: `0x180012a02`
- name: `BthServOpen`
- size: `338`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1800024ac`
- `0x1800110a0`
- `0x1800110d0`
- `0x1800110fc`
- `0x180011e70`
- `0x1800128b0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180012941`
- `RPCRT4!RpcImpersonateClient` at `0x180012941`
- `RPCRT4!RpcRevertToSelf` at `0x1800129cb`
- `RPCRT4!RpcRevertToSelf` at `0x1800129cb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800129c2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800129c2`

## pseudocode

```c
__int64 __fastcall BthServOpen(__int64 a1, _QWORD *a2, _DWORD *a3, __int64 a4)
{
  __int64 result; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  char v10; // bl
  HANDLE v11; // rbx
  char v12[56]; // [rsp+50h] [rbp-38h] BYREF

  result = BthServRpcAuthenticate(v12);
  if ( !(_DWORD)result )
  {
    v8 = MIDL_user_allocate(0x68u);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 0x68u);
      *v9 = a4;
      v9[3] = v9 + 2;
      v10 = 1;
      v9[2] = v9 + 2;
      v9[5] = v9 + 4;
      v9[4] = v9 + 4;
      v9[8] = v9 + 7;
      v9[7] = v9 + 7;
      v9[10] = v9 + 9;
      v9[9] = v9 + 9;
      *((_DWORD *)v9 + 12) = 0;
      *((_DWORD *)v9 + 22) = 1;
      if ( RpcImpersonateClient(0) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          v10 = 0;
        if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        SdpFreePool(v9);
        *a2 = 0;
        *a3 = -2147024891;
      }
      else
      {
        v11 = OpenProcess(0x40u, 0, *(_DWORD *)v9);
        RpcRevertToSelf();
        if ( v11 )
        {
          v9[1] = v11;
          *a2 = v9;
          *a3 = 0;
        }
        else
        {
          SdpFreePool(v9);
          *a2 = 0;
          *a3 = -2147024736;
        }
      }
    }
    else
    {
      *a2 = 0;
      *a3 = -2147024882;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800128b0  push    rbx
0x1800128b2  push    rsi
0x1800128b3  push    rdi
0x1800128b4  push    r14
0x1800128b6  sub     rsp, 68h
0x1800128ba  lea     rcx, [rsp+88h+var_38]; void *
0x1800128bf  mov     rbx, r9
0x1800128c2  mov     rsi, r8
0x1800128c5  mov     r14, rdx
0x1800128c8  call    ?BthServRpcAuthenticate@@YAKPEAX@Z; BthServRpcAuthenticate(void *)
0x1800128cd  test    eax, eax
0x1800128cf  jnz     loc_1800129F8
0x1800128d5  lea     ecx, [rax+68h]; size
0x1800128d8  call    MIDL_user_allocate
0x1800128dd  mov     rdi, rax
0x1800128e0  test    rax, rax
0x1800128e3  jnz     short loc_1800128F3
0x1800128e5  mov     [r14], rax
0x1800128e8  mov     dword ptr [rsi], 8007000Eh
0x1800128ee  jmp     loc_1800129F6
0x1800128f3  xor     edx, edx; Val
0x1800128f5  mov     rcx, rdi; void *
0x1800128f8  lea     r8d, [rdx+68h]; Size
0x1800128fc  call    memset_0
0x180012901  mov     [rdi], rbx
0x180012904  lea     rax, [rdi+10h]
0x180012908  mov     [rax+8], rax
0x18001290c  mov     ebx, 1
0x180012911  mov     [rax], rax
0x180012914  xor     ecx, ecx; BindingHandle
0x180012916  lea     rax, [rdi+20h]
0x18001291a  mov     [rax+8], rax
0x18001291e  mov     [rax], rax
0x180012921  lea     rax, [rdi+38h]
0x180012925  mov     [rax+8], rax
0x180012929  mov     [rax], rax
0x18001292c  lea     rax, [rdi+48h]
0x180012930  mov     [rax+8], rax
0x180012934  mov     [rax], rax
0x180012937  mov     dword ptr [rdi+30h], 0
0x18001293e  mov     [rdi+58h], ebx
0x180012941  call    cs:__imp_RpcImpersonateClient
0x180012947  test    eax, eax
0x180012949  jz      short loc_1800129BA
0x18001294b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012952  lea     rax, WPP_GLOBAL_Control
0x180012959  cmp     rcx, rax
0x18001295c  jz      short loc_180012964
0x18001295e  cmp     byte ptr [rcx+19h], 4
0x180012962  jnb     short loc_180012966
0x180012964  xor     bl, bl
0x180012966  lea     rax, WPP_RECORDER_INITIALIZED
0x18001296d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180012974  setnz   r8b
0x180012978  test    bl, bl
0x18001297a  jnz     short loc_180012981
0x18001297c  test    r8b, r8b
0x18001297f  jz      short loc_1800129A3
0x180012981  mov     r9, [rcx+28h]
0x180012985  lea     rax, WPP_efb6cd7e54bb348036d84fdff4bfab53_Traceguids
0x18001298c  mov     rcx, [rcx+10h]
0x180012990  mov     dl, bl
0x180012992  mov     [rsp+88h+var_50], rax
0x180012997  mov     [rsp+88h+var_58], 0Ch
0x18001299e  call    WPP_RECORDER_AND_TRACE_SF_s
0x1800129a3  mov     rcx, rdi
0x1800129a6  call    SdpFreePool
0x1800129ab  mov     qword ptr [r14], 0
0x1800129b2  mov     dword ptr [rsi], 80070005h
0x1800129b8  jmp     short loc_1800129F6
0x1800129ba  mov     r8d, [rdi]; dwProcessId
0x1800129bd  xor     edx, edx; bInheritHandle
0x1800129bf  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800129c2  call    cs:__imp_OpenProcess
0x1800129c8  mov     rbx, rax
0x1800129cb  call    cs:__imp_RpcRevertToSelf
0x1800129d1  test    rbx, rbx
0x1800129d4  jnz     short loc_1800129E9
0x1800129d6  mov     rcx, rdi
0x1800129d9  call    SdpFreePool
0x1800129de  mov     [r14], rbx
0x1800129e1  mov     dword ptr [rsi], 800700A0h
0x1800129e7  jmp     short loc_1800129F6
0x1800129e9  mov     [rdi+8], rbx
0x1800129ed  mov     [r14], rdi
0x1800129f0  mov     dword ptr [rsi], 0
0x1800129f6  xor     eax, eax
0x1800129f8  add     rsp, 68h
0x1800129fc  pop     r14
0x1800129fe  pop     rdi
0x1800129ff  pop     rsi
0x180012a00  pop     rbx
0x180012a01  retn
```
