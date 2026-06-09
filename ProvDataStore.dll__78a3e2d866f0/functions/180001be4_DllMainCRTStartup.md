# __DllMainCRTStartup

- ea: `0x180001be4`
- end: `0x180001df0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ba0`

## callees

- `0x180001970`
- `0x180001be4`
- `0x180001f7e`
- `0x180006c84`
- `0x180010ff0`

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
  if ( (_DWORD)fdwReason || dword_180019284 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180019288 = 1;
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
            if ( dword_180019288 )
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
0x180001be4  mov     [rsp+lpvReserved], r8
0x180001be9  mov     [rsp+arg_8], edx
0x180001bed  mov     [rsp+arg_0], rcx
0x180001bf2  push    rbx
0x180001bf3  push    rsi
0x180001bf4  push    rdi
0x180001bf5  sub     rsp, 0F0h
0x180001bfc  mov     edi, edx
0x180001bfe  mov     rsi, rcx
0x180001c01  mov     ebx, 1
0x180001c06  cmp     edx, ebx
0x180001c08  ja      short loc_180001C10
0x180001c0a  mov     cs:__native_dllmain_reason, edx
0x180001c10  test    edx, edx
0x180001c12  jnz     short loc_180001C27
0x180001c14  cmp     cs:dword_180019284, edx
0x180001c1a  jnz     short loc_180001C27
0x180001c1c  xor     ebx, ebx
0x180001c1e  mov     [rsp+108h+var_E8], ebx
0x180001c22  jmp     loc_180001DD4
0x180001c27  lea     eax, [rdx-1]
0x180001c2a  cmp     eax, 1
0x180001c2d  ja      loc_180001CB4
0x180001c33  mov     rax, cs:_pRawDllMain
0x180001c3a  test    rax, rax
0x180001c3d  jz      short loc_180001C75
0x180001c3f  cmp     edx, 1
0x180001c42  jnz     short loc_180001C4A
0x180001c44  mov     cs:dword_180019288, edx
0x180001c4a  mov     r8, [rsp+108h+lpvReserved]
0x180001c52  call    cs:__guard_dispatch_icall_fptr
0x180001c58  mov     ebx, eax
0x180001c5a  mov     [rsp+108h+var_E8], eax
0x180001c5e  jmp     short loc_180001C75
0x180001c60  xor     ebx, ebx
0x180001c62  mov     [rsp+108h+var_E8], ebx
0x180001c66  mov     edi, [rsp+108h+arg_8]
0x180001c6d  mov     rsi, [rsp+108h+arg_0]
0x180001c75  test    ebx, ebx
0x180001c77  jz      loc_180001DD4
0x180001c7d  mov     r8, [rsp+108h+lpvReserved]
0x180001c85  mov     edx, edi
0x180001c87  mov     rcx, rsi
0x180001c8a  call    _CRT_INIT
0x180001c8f  mov     ebx, eax
0x180001c91  mov     [rsp+108h+var_E8], eax
0x180001c95  jmp     short loc_180001CAC
0x180001c97  xor     ebx, ebx
0x180001c99  mov     [rsp+108h+var_E8], ebx
0x180001c9d  mov     edi, [rsp+108h+arg_8]
0x180001ca4  mov     rsi, [rsp+108h+arg_0]
0x180001cac  test    ebx, ebx
0x180001cae  jz      loc_180001DD4
0x180001cb4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x180001cbc  mov     edx, edi; fdwReason
0x180001cbe  mov     rcx, rsi; hinstDLL
0x180001cc1  call    DllMain
0x180001cc6  mov     ebx, eax
0x180001cc8  mov     [rsp+108h+var_E8], eax
0x180001ccc  jmp     short loc_180001CE3
0x180001cce  xor     ebx, ebx
0x180001cd0  mov     [rsp+108h+var_E8], ebx
0x180001cd4  mov     edi, [rsp+108h+arg_8]
0x180001cdb  mov     rsi, [rsp+108h+arg_0]
0x180001ce3  cmp     edi, 1
0x180001ce6  jnz     short loc_180001D5F
0x180001ce8  test    ebx, ebx
0x180001cea  jnz     short loc_180001D5F
0x180001cec  xor     r8d, r8d; lpvReserved
0x180001cef  xor     edx, edx; fdwReason
0x180001cf1  mov     rcx, rsi; hinstDLL
0x180001cf4  call    DllMain
0x180001cf9  jmp     short loc_180001D0E
0x180001cfb  mov     edi, [rsp+108h+arg_8]
0x180001d02  mov     rsi, [rsp+108h+arg_0]
0x180001d0a  mov     ebx, [rsp+108h+var_E8]
0x180001d0e  xor     r8d, r8d
0x180001d11  xor     edx, edx
0x180001d13  mov     rcx, rsi
0x180001d16  call    _CRT_INIT
0x180001d1b  jmp     short loc_180001D30
0x180001d1d  mov     edi, [rsp+108h+arg_8]
0x180001d24  mov     rsi, [rsp+108h+arg_0]
0x180001d2c  mov     ebx, [rsp+108h+var_E8]
0x180001d30  mov     rax, cs:_pRawDllMain
0x180001d37  test    rax, rax
0x180001d3a  jz      short loc_180001D5F
0x180001d3c  xor     r8d, r8d
0x180001d3f  xor     edx, edx
0x180001d41  mov     rcx, rsi
0x180001d44  call    cs:__guard_dispatch_icall_fptr
0x180001d4a  jmp     short loc_180001D5F
0x180001d4c  mov     edi, [rsp+108h+arg_8]
0x180001d53  mov     rsi, [rsp+108h+arg_0]
0x180001d5b  mov     ebx, [rsp+108h+var_E8]
0x180001d5f  test    edi, edi
0x180001d61  jz      short loc_180001D68
0x180001d63  cmp     edi, 3
0x180001d66  jnz     short loc_180001DD4
0x180001d68  mov     r8, [rsp+108h+lpvReserved]
0x180001d70  mov     edx, edi
0x180001d72  mov     rcx, rsi
0x180001d75  call    _CRT_INIT
0x180001d7a  mov     ebx, eax
0x180001d7c  mov     [rsp+108h+var_E8], eax
0x180001d80  jmp     short loc_180001D97
0x180001d82  xor     ebx, ebx
0x180001d84  mov     [rsp+108h+var_E8], ebx
0x180001d88  mov     edi, [rsp+108h+arg_8]
0x180001d8f  mov     rsi, [rsp+108h+arg_0]
0x180001d97  mov     rax, cs:_pRawDllMain
0x180001d9e  test    rax, rax
0x180001da1  jz      short loc_180001DD4
0x180001da3  cmp     cs:dword_180019288, 0
0x180001daa  jz      short loc_180001DD4
0x180001dac  mov     r8, [rsp+108h+lpvReserved]
0x180001db4  mov     edx, edi
0x180001db6  mov     rcx, rsi
0x180001db9  call    cs:__guard_dispatch_icall_fptr
0x180001dbf  mov     ebx, eax
0x180001dc1  mov     [rsp+108h+var_E8], eax
0x180001dc5  jmp     short loc_180001DD4
0x180001dc7  xor     ebx, ebx
0x180001dc9  mov     [rsp+108h+var_E8], ebx
0x180001dcd  mov     edi, [rsp+108h+arg_8]
0x180001dd4  cmp     edi, 1
0x180001dd7  ja      short loc_180001DE3
0x180001dd9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001de3  mov     eax, ebx
0x180001de5  add     rsp, 0F0h
0x180001dec  pop     rdi
0x180001ded  pop     rsi
0x180001dee  pop     rbx
0x180001def  retn
0x180011093  push    rbp
0x180011095  sub     rsp, 20h
0x180011099  mov     rbp, rdx
0x18001109c  mov     rax, [rcx]
0x18001109f  mov     edx, [rax]
0x1800110a1  mov     [rbp+0A8h], rcx
0x1800110a8  mov     [rbp+28h], edx
0x1800110ab  mov     eax, [rbp+28h]
0x1800110ae  cmp     eax, 0E06D7363h
0x1800110b3  jnz     short loc_1800110C9
0x1800110b5  mov     rdx, [rbp+0A8h]
0x1800110bc  mov     ecx, [rbp+28h]
0x1800110bf  call    _XcptFilter_0
0x1800110c4  mov     [rbp+30h], eax
0x1800110c7  jmp     short loc_1800110D0
0x1800110c9  mov     dword ptr [rbp+30h], 0
0x1800110d0  mov     eax, [rbp+30h]
0x1800110d3  add     rsp, 20h
0x1800110d7  pop     rbp
0x1800110d8  retn
0x1800110da  push    rbp
0x1800110dc  sub     rsp, 20h
0x1800110e0  mov     rbp, rdx
0x1800110e3  mov     rax, [rcx]
0x1800110e6  mov     edx, [rax]
0x1800110e8  mov     [rbp+0B0h], rcx
0x1800110ef  mov     [rbp+38h], edx
0x1800110f2  mov     eax, [rbp+38h]
0x1800110f5  cmp     eax, 0E06D7363h
0x1800110fa  jnz     short loc_180011110
0x1800110fc  mov     rdx, [rbp+0B0h]
0x180011103  mov     ecx, [rbp+38h]
0x180011106  call    _XcptFilter_0
0x18001110b  mov     [rbp+40h], eax
0x18001110e  jmp     short loc_180011117
0x180011110  mov     dword ptr [rbp+40h], 0
0x180011117  mov     eax, [rbp+40h]
0x18001111a  add     rsp, 20h
0x18001111e  pop     rbp
0x18001111f  retn
0x180011121  push    rbp
0x180011123  sub     rsp, 20h
0x180011127  mov     rbp, rdx
0x18001112a  mov     rax, [rcx]
0x18001112d  mov     edx, [rax]
0x18001112f  mov     [rbp+0B8h], rcx
0x180011136  mov     [rbp+48h], edx
0x180011139  mov     eax, [rbp+48h]
0x18001113c  cmp     eax, 0E06D7363h
0x180011141  jnz     short loc_180011157
0x180011143  mov     rdx, [rbp+0B8h]
0x18001114a  mov     ecx, [rbp+48h]
0x18001114d  call    _XcptFilter_0
0x180011152  mov     [rbp+50h], eax
0x180011155  jmp     short loc_18001115E
0x180011157  mov     dword ptr [rbp+50h], 0
0x18001115e  mov     eax, [rbp+50h]
0x180011161  add     rsp, 20h
0x180011165  pop     rbp
0x180011166  retn
0x180011168  push    rbp
0x18001116a  sub     rsp, 20h
0x18001116e  mov     rbp, rdx
0x180011171  mov     rax, [rcx]
0x180011174  mov     edx, [rax]
0x180011176  mov     [rbp+0C0h], rcx
0x18001117d  mov     [rbp+58h], edx
0x180011180  mov     eax, [rbp+58h]
0x180011183  cmp     eax, 0E06D7363h
0x180011188  jnz     short loc_18001119E
0x18001118a  mov     rdx, [rbp+0C0h]
0x180011191  mov     ecx, [rbp+58h]
0x180011194  call    _XcptFilter_0
0x180011199  mov     [rbp+60h], eax
0x18001119c  jmp     short loc_1800111A5
0x18001119e  mov     dword ptr [rbp+60h], 0
0x1800111a5  mov     eax, [rbp+60h]
0x1800111a8  add     rsp, 20h
0x1800111ac  pop     rbp
0x1800111ad  retn
0x1800111af  push    rbp
0x1800111b1  sub     rsp, 20h
0x1800111b5  mov     rbp, rdx
0x1800111b8  mov     rax, [rcx]
0x1800111bb  mov     edx, [rax]
0x1800111bd  mov     [rbp+0C8h], rcx
0x1800111c4  mov     [rbp+68h], edx
0x1800111c7  mov     eax, [rbp+68h]
0x1800111ca  cmp     eax, 0E06D7363h
0x1800111cf  jnz     short loc_1800111E5
0x1800111d1  mov     rdx, [rbp+0C8h]
0x1800111d8  mov     ecx, [rbp+68h]
0x1800111db  call    _XcptFilter_0
0x1800111e0  mov     [rbp+70h], eax
0x1800111e3  jmp     short loc_1800111EC
0x1800111e5  mov     dword ptr [rbp+70h], 0
0x1800111ec  mov     eax, [rbp+70h]
0x1800111ef  add     rsp, 20h
0x1800111f3  pop     rbp
0x1800111f4  retn
0x1800111f6  push    rbp
0x1800111f8  sub     rsp, 20h
0x1800111fc  mov     rbp, rdx
0x1800111ff  mov     rax, [rcx]
0x180011202  mov     edx, [rax]
0x180011204  mov     [rbp+0D0h], rcx
0x18001120b  mov     [rbp+78h], edx
0x18001120e  mov     eax, [rbp+78h]
0x180011211  cmp     eax, 0E06D7363h
0x180011216  jnz     short loc_18001122F
0x180011218  mov     rdx, [rbp+0D0h]
0x18001121f  mov     ecx, [rbp+78h]
0x180011222  call    _XcptFilter_0
0x180011227  mov     [rbp+80h], eax
0x18001122d  jmp     short loc_180011239
0x18001122f  mov     dword ptr [rbp+80h], 0
0x180011239  mov     eax, [rbp+80h]
0x18001123f  add     rsp, 20h
0x180011243  pop     rbp
0x180011244  retn
0x180011246  push    rbp
0x180011248  sub     rsp, 20h
0x18001124c  mov     rbp, rdx
0x18001124f  mov     rax, [rcx]
0x180011252  mov     edx, [rax]
0x180011254  mov     [rbp+0D8h], rcx
0x18001125b  mov     [rbp+88h], edx
0x180011261  mov     eax, [rbp+88h]
0x180011267  cmp     eax, 0E06D7363h
0x18001126c  jnz     short loc_180011288
0x18001126e  mov     rdx, [rbp+0D8h]
0x180011275  mov     ecx, [rbp+88h]
0x18001127b  call    _XcptFilter_0
0x180011280  mov     [rbp+90h], eax
0x180011286  jmp     short loc_180011292
0x180011288  mov     dword ptr [rbp+90h], 0
0x180011292  mov     eax, [rbp+90h]
0x180011298  add     rsp, 20h
0x18001129c  pop     rbp
0x18001129d  retn
0x18001129f  push    rbp
0x1800112a1  sub     rsp, 20h
0x1800112a5  mov     rbp, rdx
0x1800112a8  mov     rax, [rcx]
0x1800112ab  mov     edx, [rax]
0x1800112ad  mov     [rbp+0E0h], rcx
0x1800112b4  mov     [rbp+98h], edx
0x1800112ba  mov     eax, [rbp+98h]
0x1800112c0  cmp     eax, 0E06D7363h
0x1800112c5  jnz     short loc_1800112E1
0x1800112c7  mov     rdx, [rbp+0E0h]
0x1800112ce  mov     ecx, [rbp+98h]
0x1800112d4  call    _XcptFilter_0
0x1800112d9  mov     [rbp+0A0h], eax
0x1800112df  jmp     short loc_1800112EB
0x1800112e1  mov     dword ptr [rbp+0A0h], 0
0x1800112eb  mov     eax, [rbp+0A0h]
0x1800112f1  add     rsp, 20h
0x1800112f5  pop     rbp
0x1800112f6  retn
0x1800112f8  push    rbp
0x1800112fa  sub     rsp, 20h
0x1800112fe  mov     rbp, rdx
0x180011301  cmp     dword ptr [rbp+118h], 1
0x180011308  ja      short loc_180011314
0x18001130a  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
