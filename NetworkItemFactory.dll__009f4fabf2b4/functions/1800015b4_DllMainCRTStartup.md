# __DllMainCRTStartup

- ea: `0x1800015b4`
- end: `0x1800017c0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001570`

## callees

- `0x180001340`
- `0x1800015b4`
- `0x180001966`
- `0x180007314`
- `0x18000a840`

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
  if ( (_DWORD)fdwReason || dword_18001120C )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180011210 = 1;
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
            if ( dword_180011210 )
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
0x1800015b4  mov     [rsp+lpvReserved], r8
0x1800015b9  mov     [rsp+arg_8], edx
0x1800015bd  mov     [rsp+arg_0], rcx
0x1800015c2  push    rbx
0x1800015c3  push    rsi
0x1800015c4  push    rdi
0x1800015c5  sub     rsp, 0F0h
0x1800015cc  mov     edi, edx
0x1800015ce  mov     rsi, rcx
0x1800015d1  mov     ebx, 1
0x1800015d6  cmp     edx, ebx
0x1800015d8  ja      short loc_1800015E0
0x1800015da  mov     cs:__native_dllmain_reason, edx
0x1800015e0  test    edx, edx
0x1800015e2  jnz     short loc_1800015F7
0x1800015e4  cmp     cs:dword_18001120C, edx
0x1800015ea  jnz     short loc_1800015F7
0x1800015ec  xor     ebx, ebx
0x1800015ee  mov     [rsp+108h+var_E8], ebx
0x1800015f2  jmp     loc_1800017A4
0x1800015f7  lea     eax, [rdx-1]
0x1800015fa  cmp     eax, 1
0x1800015fd  ja      loc_180001684
0x180001603  mov     rax, cs:_pRawDllMain
0x18000160a  test    rax, rax
0x18000160d  jz      short loc_180001645
0x18000160f  cmp     edx, 1
0x180001612  jnz     short loc_18000161A
0x180001614  mov     cs:dword_180011210, edx
0x18000161a  mov     r8, [rsp+108h+lpvReserved]
0x180001622  call    cs:__guard_dispatch_icall_fptr
0x180001628  mov     ebx, eax
0x18000162a  mov     [rsp+108h+var_E8], eax
0x18000162e  jmp     short loc_180001645
0x180001630  xor     ebx, ebx
0x180001632  mov     [rsp+108h+var_E8], ebx
0x180001636  mov     edi, [rsp+108h+arg_8]
0x18000163d  mov     rsi, [rsp+108h+arg_0]
0x180001645  test    ebx, ebx
0x180001647  jz      loc_1800017A4
0x18000164d  mov     r8, [rsp+108h+lpvReserved]
0x180001655  mov     edx, edi
0x180001657  mov     rcx, rsi
0x18000165a  call    _CRT_INIT
0x18000165f  mov     ebx, eax
0x180001661  mov     [rsp+108h+var_E8], eax
0x180001665  jmp     short loc_18000167C
0x180001667  xor     ebx, ebx
0x180001669  mov     [rsp+108h+var_E8], ebx
0x18000166d  mov     edi, [rsp+108h+arg_8]
0x180001674  mov     rsi, [rsp+108h+arg_0]
0x18000167c  test    ebx, ebx
0x18000167e  jz      loc_1800017A4
0x180001684  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000168c  mov     edx, edi; fdwReason
0x18000168e  mov     rcx, rsi; hinstDLL
0x180001691  call    DllMain
0x180001696  mov     ebx, eax
0x180001698  mov     [rsp+108h+var_E8], eax
0x18000169c  jmp     short loc_1800016B3
0x18000169e  xor     ebx, ebx
0x1800016a0  mov     [rsp+108h+var_E8], ebx
0x1800016a4  mov     edi, [rsp+108h+arg_8]
0x1800016ab  mov     rsi, [rsp+108h+arg_0]
0x1800016b3  cmp     edi, 1
0x1800016b6  jnz     short loc_18000172F
0x1800016b8  test    ebx, ebx
0x1800016ba  jnz     short loc_18000172F
0x1800016bc  xor     r8d, r8d; lpvReserved
0x1800016bf  xor     edx, edx; fdwReason
0x1800016c1  mov     rcx, rsi; hinstDLL
0x1800016c4  call    DllMain
0x1800016c9  jmp     short loc_1800016DE
0x1800016cb  mov     edi, [rsp+108h+arg_8]
0x1800016d2  mov     rsi, [rsp+108h+arg_0]
0x1800016da  mov     ebx, [rsp+108h+var_E8]
0x1800016de  xor     r8d, r8d
0x1800016e1  xor     edx, edx
0x1800016e3  mov     rcx, rsi
0x1800016e6  call    _CRT_INIT
0x1800016eb  jmp     short loc_180001700
0x1800016ed  mov     edi, [rsp+108h+arg_8]
0x1800016f4  mov     rsi, [rsp+108h+arg_0]
0x1800016fc  mov     ebx, [rsp+108h+var_E8]
0x180001700  mov     rax, cs:_pRawDllMain
0x180001707  test    rax, rax
0x18000170a  jz      short loc_18000172F
0x18000170c  xor     r8d, r8d
0x18000170f  xor     edx, edx
0x180001711  mov     rcx, rsi
0x180001714  call    cs:__guard_dispatch_icall_fptr
0x18000171a  jmp     short loc_18000172F
0x18000171c  mov     edi, [rsp+108h+arg_8]
0x180001723  mov     rsi, [rsp+108h+arg_0]
0x18000172b  mov     ebx, [rsp+108h+var_E8]
0x18000172f  test    edi, edi
0x180001731  jz      short loc_180001738
0x180001733  cmp     edi, 3
0x180001736  jnz     short loc_1800017A4
0x180001738  mov     r8, [rsp+108h+lpvReserved]
0x180001740  mov     edx, edi
0x180001742  mov     rcx, rsi
0x180001745  call    _CRT_INIT
0x18000174a  mov     ebx, eax
0x18000174c  mov     [rsp+108h+var_E8], eax
0x180001750  jmp     short loc_180001767
0x180001752  xor     ebx, ebx
0x180001754  mov     [rsp+108h+var_E8], ebx
0x180001758  mov     edi, [rsp+108h+arg_8]
0x18000175f  mov     rsi, [rsp+108h+arg_0]
0x180001767  mov     rax, cs:_pRawDllMain
0x18000176e  test    rax, rax
0x180001771  jz      short loc_1800017A4
0x180001773  cmp     cs:dword_180011210, 0
0x18000177a  jz      short loc_1800017A4
0x18000177c  mov     r8, [rsp+108h+lpvReserved]
0x180001784  mov     edx, edi
0x180001786  mov     rcx, rsi
0x180001789  call    cs:__guard_dispatch_icall_fptr
0x18000178f  mov     ebx, eax
0x180001791  mov     [rsp+108h+var_E8], eax
0x180001795  jmp     short loc_1800017A4
0x180001797  xor     ebx, ebx
0x180001799  mov     [rsp+108h+var_E8], ebx
0x18000179d  mov     edi, [rsp+108h+arg_8]
0x1800017a4  cmp     edi, 1
0x1800017a7  ja      short loc_1800017B3
0x1800017a9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800017b3  mov     eax, ebx
0x1800017b5  add     rsp, 0F0h
0x1800017bc  pop     rdi
0x1800017bd  pop     rsi
0x1800017be  pop     rbx
0x1800017bf  retn
0x18000a880  push    rbp
0x18000a882  sub     rsp, 20h
0x18000a886  mov     rbp, rdx
0x18000a889  mov     rax, [rcx]
0x18000a88c  mov     edx, [rax]
0x18000a88e  mov     [rbp+0A8h], rcx
0x18000a895  mov     [rbp+28h], edx
0x18000a898  mov     eax, [rbp+28h]
0x18000a89b  cmp     eax, 0E06D7363h
0x18000a8a0  jnz     short loc_18000A8B6
0x18000a8a2  mov     rdx, [rbp+0A8h]
0x18000a8a9  mov     ecx, [rbp+28h]
0x18000a8ac  call    _XcptFilter_0
0x18000a8b1  mov     [rbp+30h], eax
0x18000a8b4  jmp     short loc_18000A8BD
0x18000a8b6  mov     dword ptr [rbp+30h], 0
0x18000a8bd  mov     eax, [rbp+30h]
0x18000a8c0  add     rsp, 20h
0x18000a8c4  pop     rbp
0x18000a8c5  retn
0x18000a8c7  push    rbp
0x18000a8c9  sub     rsp, 20h
0x18000a8cd  mov     rbp, rdx
0x18000a8d0  mov     rax, [rcx]
0x18000a8d3  mov     edx, [rax]
0x18000a8d5  mov     [rbp+0B0h], rcx
0x18000a8dc  mov     [rbp+38h], edx
0x18000a8df  mov     eax, [rbp+38h]
0x18000a8e2  cmp     eax, 0E06D7363h
0x18000a8e7  jnz     short loc_18000A8FD
0x18000a8e9  mov     rdx, [rbp+0B0h]
0x18000a8f0  mov     ecx, [rbp+38h]
0x18000a8f3  call    _XcptFilter_0
0x18000a8f8  mov     [rbp+40h], eax
0x18000a8fb  jmp     short loc_18000A904
0x18000a8fd  mov     dword ptr [rbp+40h], 0
0x18000a904  mov     eax, [rbp+40h]
0x18000a907  add     rsp, 20h
0x18000a90b  pop     rbp
0x18000a90c  retn
0x18000a90e  push    rbp
0x18000a910  sub     rsp, 20h
0x18000a914  mov     rbp, rdx
0x18000a917  mov     rax, [rcx]
0x18000a91a  mov     edx, [rax]
0x18000a91c  mov     [rbp+0B8h], rcx
0x18000a923  mov     [rbp+48h], edx
0x18000a926  mov     eax, [rbp+48h]
0x18000a929  cmp     eax, 0E06D7363h
0x18000a92e  jnz     short loc_18000A944
0x18000a930  mov     rdx, [rbp+0B8h]
0x18000a937  mov     ecx, [rbp+48h]
0x18000a93a  call    _XcptFilter_0
0x18000a93f  mov     [rbp+50h], eax
0x18000a942  jmp     short loc_18000A94B
0x18000a944  mov     dword ptr [rbp+50h], 0
0x18000a94b  mov     eax, [rbp+50h]
0x18000a94e  add     rsp, 20h
0x18000a952  pop     rbp
0x18000a953  retn
0x18000a955  push    rbp
0x18000a957  sub     rsp, 20h
0x18000a95b  mov     rbp, rdx
0x18000a95e  mov     rax, [rcx]
0x18000a961  mov     edx, [rax]
0x18000a963  mov     [rbp+0C0h], rcx
0x18000a96a  mov     [rbp+58h], edx
0x18000a96d  mov     eax, [rbp+58h]
0x18000a970  cmp     eax, 0E06D7363h
0x18000a975  jnz     short loc_18000A98B
0x18000a977  mov     rdx, [rbp+0C0h]
0x18000a97e  mov     ecx, [rbp+58h]
0x18000a981  call    _XcptFilter_0
0x18000a986  mov     [rbp+60h], eax
0x18000a989  jmp     short loc_18000A992
0x18000a98b  mov     dword ptr [rbp+60h], 0
0x18000a992  mov     eax, [rbp+60h]
0x18000a995  add     rsp, 20h
0x18000a999  pop     rbp
0x18000a99a  retn
0x18000a99c  push    rbp
0x18000a99e  sub     rsp, 20h
0x18000a9a2  mov     rbp, rdx
0x18000a9a5  mov     rax, [rcx]
0x18000a9a8  mov     edx, [rax]
0x18000a9aa  mov     [rbp+0C8h], rcx
0x18000a9b1  mov     [rbp+68h], edx
0x18000a9b4  mov     eax, [rbp+68h]
0x18000a9b7  cmp     eax, 0E06D7363h
0x18000a9bc  jnz     short loc_18000A9D2
0x18000a9be  mov     rdx, [rbp+0C8h]
0x18000a9c5  mov     ecx, [rbp+68h]
0x18000a9c8  call    _XcptFilter_0
0x18000a9cd  mov     [rbp+70h], eax
0x18000a9d0  jmp     short loc_18000A9D9
0x18000a9d2  mov     dword ptr [rbp+70h], 0
0x18000a9d9  mov     eax, [rbp+70h]
0x18000a9dc  add     rsp, 20h
0x18000a9e0  pop     rbp
0x18000a9e1  retn
0x18000a9e3  push    rbp
0x18000a9e5  sub     rsp, 20h
0x18000a9e9  mov     rbp, rdx
0x18000a9ec  mov     rax, [rcx]
0x18000a9ef  mov     edx, [rax]
0x18000a9f1  mov     [rbp+0D0h], rcx
0x18000a9f8  mov     [rbp+78h], edx
0x18000a9fb  mov     eax, [rbp+78h]
0x18000a9fe  cmp     eax, 0E06D7363h
0x18000aa03  jnz     short loc_18000AA1C
0x18000aa05  mov     rdx, [rbp+0D0h]
0x18000aa0c  mov     ecx, [rbp+78h]
0x18000aa0f  call    _XcptFilter_0
0x18000aa14  mov     [rbp+80h], eax
0x18000aa1a  jmp     short loc_18000AA26
0x18000aa1c  mov     dword ptr [rbp+80h], 0
0x18000aa26  mov     eax, [rbp+80h]
0x18000aa2c  add     rsp, 20h
0x18000aa30  pop     rbp
0x18000aa31  retn
0x18000aa33  push    rbp
0x18000aa35  sub     rsp, 20h
0x18000aa39  mov     rbp, rdx
0x18000aa3c  mov     rax, [rcx]
0x18000aa3f  mov     edx, [rax]
0x18000aa41  mov     [rbp+0D8h], rcx
0x18000aa48  mov     [rbp+88h], edx
0x18000aa4e  mov     eax, [rbp+88h]
0x18000aa54  cmp     eax, 0E06D7363h
0x18000aa59  jnz     short loc_18000AA75
0x18000aa5b  mov     rdx, [rbp+0D8h]
0x18000aa62  mov     ecx, [rbp+88h]
0x18000aa68  call    _XcptFilter_0
0x18000aa6d  mov     [rbp+90h], eax
0x18000aa73  jmp     short loc_18000AA7F
0x18000aa75  mov     dword ptr [rbp+90h], 0
0x18000aa7f  mov     eax, [rbp+90h]
0x18000aa85  add     rsp, 20h
0x18000aa89  pop     rbp
0x18000aa8a  retn
0x18000aa8c  push    rbp
0x18000aa8e  sub     rsp, 20h
0x18000aa92  mov     rbp, rdx
0x18000aa95  mov     rax, [rcx]
0x18000aa98  mov     edx, [rax]
0x18000aa9a  mov     [rbp+0E0h], rcx
0x18000aaa1  mov     [rbp+98h], edx
0x18000aaa7  mov     eax, [rbp+98h]
0x18000aaad  cmp     eax, 0E06D7363h
0x18000aab2  jnz     short loc_18000AACE
0x18000aab4  mov     rdx, [rbp+0E0h]
0x18000aabb  mov     ecx, [rbp+98h]
0x18000aac1  call    _XcptFilter_0
0x18000aac6  mov     [rbp+0A0h], eax
0x18000aacc  jmp     short loc_18000AAD8
0x18000aace  mov     dword ptr [rbp+0A0h], 0
0x18000aad8  mov     eax, [rbp+0A0h]
0x18000aade  add     rsp, 20h
0x18000aae2  pop     rbp
0x18000aae3  retn
0x18000aae5  push    rbp
0x18000aae7  sub     rsp, 20h
0x18000aaeb  mov     rbp, rdx
0x18000aaee  cmp     dword ptr [rbp+118h], 1
0x18000aaf5  ja      short loc_18000AB01
0x18000aaf7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
