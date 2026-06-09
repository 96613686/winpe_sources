# __DllMainCRTStartup

- ea: `0x180001d04`
- end: `0x180001f10`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001cc0`

## callees

- `0x180001a90`
- `0x180001d04`
- `0x1800021e5`
- `0x180004030`
- `0x18000b750`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_180015300 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180015304 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_180015304 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180001d04  mov     [rsp+lpvReserved], r8
0x180001d09  mov     [rsp+arg_8], edx
0x180001d0d  mov     [rsp+arg_0], rcx
0x180001d12  push    rbx
0x180001d13  push    rsi
0x180001d14  push    rdi
0x180001d15  sub     rsp, 0F0h
0x180001d1c  mov     edi, edx
0x180001d1e  mov     rsi, rcx
0x180001d21  mov     ebx, 1
0x180001d26  cmp     edx, ebx
0x180001d28  ja      short loc_180001D30
0x180001d2a  mov     cs:__native_dllmain_reason, edx
0x180001d30  test    edx, edx
0x180001d32  jnz     short loc_180001D47
0x180001d34  cmp     cs:dword_180015300, edx
0x180001d3a  jnz     short loc_180001D47
0x180001d3c  xor     ebx, ebx
0x180001d3e  mov     [rsp+108h+var_E8], ebx
0x180001d42  jmp     loc_180001EF4
0x180001d47  lea     eax, [rdx-1]
0x180001d4a  cmp     eax, 1
0x180001d4d  ja      loc_180001DD4
0x180001d53  mov     rax, cs:_pRawDllMain
0x180001d5a  test    rax, rax
0x180001d5d  jz      short loc_180001D95
0x180001d5f  cmp     edx, 1
0x180001d62  jnz     short loc_180001D6A
0x180001d64  mov     cs:dword_180015304, edx
0x180001d6a  mov     r8, [rsp+108h+lpvReserved]
0x180001d72  call    cs:__guard_dispatch_icall_fptr
0x180001d78  mov     ebx, eax
0x180001d7a  mov     [rsp+108h+var_E8], eax
0x180001d7e  jmp     short loc_180001D95
0x180001d80  xor     ebx, ebx
0x180001d82  mov     [rsp+108h+var_E8], ebx
0x180001d86  mov     edi, [rsp+108h+arg_8]
0x180001d8d  mov     rsi, [rsp+108h+arg_0]
0x180001d95  test    ebx, ebx
0x180001d97  jz      loc_180001EF4
0x180001d9d  mov     r8, [rsp+108h+lpvReserved]
0x180001da5  mov     edx, edi
0x180001da7  mov     rcx, rsi
0x180001daa  call    _CRT_INIT
0x180001daf  mov     ebx, eax
0x180001db1  mov     [rsp+108h+var_E8], eax
0x180001db5  jmp     short loc_180001DCC
0x180001db7  xor     ebx, ebx
0x180001db9  mov     [rsp+108h+var_E8], ebx
0x180001dbd  mov     edi, [rsp+108h+arg_8]
0x180001dc4  mov     rsi, [rsp+108h+arg_0]
0x180001dcc  test    ebx, ebx
0x180001dce  jz      loc_180001EF4
0x180001dd4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001ddc  mov     edx, edi; fdwReason
0x180001dde  mov     rcx, rsi; hinstDLL
0x180001de1  call    DllMain
0x180001de6  mov     ebx, eax
0x180001de8  mov     [rsp+108h+var_E8], eax
0x180001dec  jmp     short loc_180001E03
0x180001dee  xor     ebx, ebx
0x180001df0  mov     [rsp+108h+var_E8], ebx
0x180001df4  mov     edi, [rsp+108h+arg_8]
0x180001dfb  mov     rsi, [rsp+108h+arg_0]
0x180001e03  cmp     edi, 1
0x180001e06  jnz     short loc_180001E7F
0x180001e08  test    ebx, ebx
0x180001e0a  jnz     short loc_180001E7F
0x180001e0c  xor     r8d, r8d; lpvReserved
0x180001e0f  xor     edx, edx; fdwReason
0x180001e11  mov     rcx, rsi; hinstDLL
0x180001e14  call    DllMain
0x180001e19  jmp     short loc_180001E2E
0x180001e1b  mov     edi, [rsp+108h+arg_8]
0x180001e22  mov     rsi, [rsp+108h+arg_0]
0x180001e2a  mov     ebx, [rsp+108h+var_E8]
0x180001e2e  xor     r8d, r8d
0x180001e31  xor     edx, edx
0x180001e33  mov     rcx, rsi
0x180001e36  call    _CRT_INIT
0x180001e3b  jmp     short loc_180001E50
0x180001e3d  mov     edi, [rsp+108h+arg_8]
0x180001e44  mov     rsi, [rsp+108h+arg_0]
0x180001e4c  mov     ebx, [rsp+108h+var_E8]
0x180001e50  mov     rax, cs:_pRawDllMain
0x180001e57  test    rax, rax
0x180001e5a  jz      short loc_180001E7F
0x180001e5c  xor     r8d, r8d
0x180001e5f  xor     edx, edx
0x180001e61  mov     rcx, rsi
0x180001e64  call    cs:__guard_dispatch_icall_fptr
0x180001e6a  jmp     short loc_180001E7F
0x180001e6c  mov     edi, [rsp+108h+arg_8]
0x180001e73  mov     rsi, [rsp+108h+arg_0]
0x180001e7b  mov     ebx, [rsp+108h+var_E8]
0x180001e7f  test    edi, edi
0x180001e81  jz      short loc_180001E88
0x180001e83  cmp     edi, 3
0x180001e86  jnz     short loc_180001EF4
0x180001e88  mov     r8, [rsp+108h+lpvReserved]
0x180001e90  mov     edx, edi
0x180001e92  mov     rcx, rsi
0x180001e95  call    _CRT_INIT
0x180001e9a  mov     ebx, eax
0x180001e9c  mov     [rsp+108h+var_E8], eax
0x180001ea0  jmp     short loc_180001EB7
0x180001ea2  xor     ebx, ebx
0x180001ea4  mov     [rsp+108h+var_E8], ebx
0x180001ea8  mov     edi, [rsp+108h+arg_8]
0x180001eaf  mov     rsi, [rsp+108h+arg_0]
0x180001eb7  mov     rax, cs:_pRawDllMain
0x180001ebe  test    rax, rax
0x180001ec1  jz      short loc_180001EF4
0x180001ec3  cmp     cs:dword_180015304, 0
0x180001eca  jz      short loc_180001EF4
0x180001ecc  mov     r8, [rsp+108h+lpvReserved]
0x180001ed4  mov     edx, edi
0x180001ed6  mov     rcx, rsi
0x180001ed9  call    cs:__guard_dispatch_icall_fptr
0x180001edf  mov     ebx, eax
0x180001ee1  mov     [rsp+108h+var_E8], eax
0x180001ee5  jmp     short loc_180001EF4
0x180001ee7  xor     ebx, ebx
0x180001ee9  mov     [rsp+108h+var_E8], ebx
0x180001eed  mov     edi, [rsp+108h+arg_8]
0x180001ef4  cmp     edi, 1
0x180001ef7  ja      short loc_180001F03
0x180001ef9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001f03  mov     eax, ebx
0x180001f05  add     rsp, 0F0h
0x180001f0c  pop     rdi
0x180001f0d  pop     rsi
0x180001f0e  pop     rbx
0x180001f0f  retn
0x18000b820  push    rbp
0x18000b822  sub     rsp, 20h
0x18000b826  mov     rbp, rdx
0x18000b829  mov     rax, [rcx]
0x18000b82c  mov     edx, [rax]
0x18000b82e  mov     [rbp+0A8h], rcx
0x18000b835  mov     [rbp+28h], edx
0x18000b838  mov     eax, [rbp+28h]
0x18000b83b  cmp     eax, 0E06D7363h
0x18000b840  jnz     short loc_18000B856
0x18000b842  mov     rdx, [rbp+0A8h]
0x18000b849  mov     ecx, [rbp+28h]
0x18000b84c  call    _XcptFilter_0
0x18000b851  mov     [rbp+30h], eax
0x18000b854  jmp     short loc_18000B85D
0x18000b856  mov     dword ptr [rbp+30h], 0
0x18000b85d  mov     eax, [rbp+30h]
0x18000b860  add     rsp, 20h
0x18000b864  pop     rbp
0x18000b865  retn
0x18000b867  push    rbp
0x18000b869  sub     rsp, 20h
0x18000b86d  mov     rbp, rdx
0x18000b870  mov     rax, [rcx]
0x18000b873  mov     edx, [rax]
0x18000b875  mov     [rbp+0B0h], rcx
0x18000b87c  mov     [rbp+38h], edx
0x18000b87f  mov     eax, [rbp+38h]
0x18000b882  cmp     eax, 0E06D7363h
0x18000b887  jnz     short loc_18000B89D
0x18000b889  mov     rdx, [rbp+0B0h]
0x18000b890  mov     ecx, [rbp+38h]
0x18000b893  call    _XcptFilter_0
0x18000b898  mov     [rbp+40h], eax
0x18000b89b  jmp     short loc_18000B8A4
0x18000b89d  mov     dword ptr [rbp+40h], 0
0x18000b8a4  mov     eax, [rbp+40h]
0x18000b8a7  add     rsp, 20h
0x18000b8ab  pop     rbp
0x18000b8ac  retn
0x18000b8ae  push    rbp
0x18000b8b0  sub     rsp, 20h
0x18000b8b4  mov     rbp, rdx
0x18000b8b7  mov     rax, [rcx]
0x18000b8ba  mov     edx, [rax]
0x18000b8bc  mov     [rbp+0B8h], rcx
0x18000b8c3  mov     [rbp+48h], edx
0x18000b8c6  mov     eax, [rbp+48h]
0x18000b8c9  cmp     eax, 0E06D7363h
0x18000b8ce  jnz     short loc_18000B8E4
0x18000b8d0  mov     rdx, [rbp+0B8h]
0x18000b8d7  mov     ecx, [rbp+48h]
0x18000b8da  call    _XcptFilter_0
0x18000b8df  mov     [rbp+50h], eax
0x18000b8e2  jmp     short loc_18000B8EB
0x18000b8e4  mov     dword ptr [rbp+50h], 0
0x18000b8eb  mov     eax, [rbp+50h]
0x18000b8ee  add     rsp, 20h
0x18000b8f2  pop     rbp
0x18000b8f3  retn
0x18000b8f5  push    rbp
0x18000b8f7  sub     rsp, 20h
0x18000b8fb  mov     rbp, rdx
0x18000b8fe  mov     rax, [rcx]
0x18000b901  mov     edx, [rax]
0x18000b903  mov     [rbp+0C0h], rcx
0x18000b90a  mov     [rbp+58h], edx
0x18000b90d  mov     eax, [rbp+58h]
0x18000b910  cmp     eax, 0E06D7363h
0x18000b915  jnz     short loc_18000B92B
0x18000b917  mov     rdx, [rbp+0C0h]
0x18000b91e  mov     ecx, [rbp+58h]
0x18000b921  call    _XcptFilter_0
0x18000b926  mov     [rbp+60h], eax
0x18000b929  jmp     short loc_18000B932
0x18000b92b  mov     dword ptr [rbp+60h], 0
0x18000b932  mov     eax, [rbp+60h]
0x18000b935  add     rsp, 20h
0x18000b939  pop     rbp
0x18000b93a  retn
0x18000b93c  push    rbp
0x18000b93e  sub     rsp, 20h
0x18000b942  mov     rbp, rdx
0x18000b945  mov     rax, [rcx]
0x18000b948  mov     edx, [rax]
0x18000b94a  mov     [rbp+0C8h], rcx
0x18000b951  mov     [rbp+68h], edx
0x18000b954  mov     eax, [rbp+68h]
0x18000b957  cmp     eax, 0E06D7363h
0x18000b95c  jnz     short loc_18000B972
0x18000b95e  mov     rdx, [rbp+0C8h]
0x18000b965  mov     ecx, [rbp+68h]
0x18000b968  call    _XcptFilter_0
0x18000b96d  mov     [rbp+70h], eax
0x18000b970  jmp     short loc_18000B979
0x18000b972  mov     dword ptr [rbp+70h], 0
0x18000b979  mov     eax, [rbp+70h]
0x18000b97c  add     rsp, 20h
0x18000b980  pop     rbp
0x18000b981  retn
0x18000b983  push    rbp
0x18000b985  sub     rsp, 20h
0x18000b989  mov     rbp, rdx
0x18000b98c  mov     rax, [rcx]
0x18000b98f  mov     edx, [rax]
0x18000b991  mov     [rbp+0D0h], rcx
0x18000b998  mov     [rbp+78h], edx
0x18000b99b  mov     eax, [rbp+78h]
0x18000b99e  cmp     eax, 0E06D7363h
0x18000b9a3  jnz     short loc_18000B9BC
0x18000b9a5  mov     rdx, [rbp+0D0h]
0x18000b9ac  mov     ecx, [rbp+78h]
0x18000b9af  call    _XcptFilter_0
0x18000b9b4  mov     [rbp+80h], eax
0x18000b9ba  jmp     short loc_18000B9C6
0x18000b9bc  mov     dword ptr [rbp+80h], 0
0x18000b9c6  mov     eax, [rbp+80h]
0x18000b9cc  add     rsp, 20h
0x18000b9d0  pop     rbp
0x18000b9d1  retn
0x18000b9d3  push    rbp
0x18000b9d5  sub     rsp, 20h
0x18000b9d9  mov     rbp, rdx
0x18000b9dc  mov     rax, [rcx]
0x18000b9df  mov     edx, [rax]
0x18000b9e1  mov     [rbp+0D8h], rcx
0x18000b9e8  mov     [rbp+88h], edx
0x18000b9ee  mov     eax, [rbp+88h]
0x18000b9f4  cmp     eax, 0E06D7363h
0x18000b9f9  jnz     short loc_18000BA15
0x18000b9fb  mov     rdx, [rbp+0D8h]
0x18000ba02  mov     ecx, [rbp+88h]
0x18000ba08  call    _XcptFilter_0
0x18000ba0d  mov     [rbp+90h], eax
0x18000ba13  jmp     short loc_18000BA1F
0x18000ba15  mov     dword ptr [rbp+90h], 0
0x18000ba1f  mov     eax, [rbp+90h]
0x18000ba25  add     rsp, 20h
0x18000ba29  pop     rbp
0x18000ba2a  retn
0x18000ba2c  push    rbp
0x18000ba2e  sub     rsp, 20h
0x18000ba32  mov     rbp, rdx
0x18000ba35  mov     rax, [rcx]
0x18000ba38  mov     edx, [rax]
0x18000ba3a  mov     [rbp+0E0h], rcx
0x18000ba41  mov     [rbp+98h], edx
0x18000ba47  mov     eax, [rbp+98h]
0x18000ba4d  cmp     eax, 0E06D7363h
0x18000ba52  jnz     short loc_18000BA6E
0x18000ba54  mov     rdx, [rbp+0E0h]
0x18000ba5b  mov     ecx, [rbp+98h]
0x18000ba61  call    _XcptFilter_0
0x18000ba66  mov     [rbp+0A0h], eax
0x18000ba6c  jmp     short loc_18000BA78
0x18000ba6e  mov     dword ptr [rbp+0A0h], 0
0x18000ba78  mov     eax, [rbp+0A0h]
0x18000ba7e  add     rsp, 20h
0x18000ba82  pop     rbp
0x18000ba83  retn
0x18000ba85  push    rbp
0x18000ba87  sub     rsp, 20h
0x18000ba8b  mov     rbp, rdx
0x18000ba8e  cmp     dword ptr [rbp+118h], 1
0x18000ba95  ja      short loc_18000BAA1
0x18000ba97  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
