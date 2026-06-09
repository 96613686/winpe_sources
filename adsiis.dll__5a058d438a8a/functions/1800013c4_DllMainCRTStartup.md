# __DllMainCRTStartup

- ea: `0x1800013c4`
- end: `0x1800015d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001380`

## callees

- `0x180001150`
- `0x1800013c4`
- `0x180001810`
- `0x180016988`
- `0x18001d700`

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
  if ( (_DWORD)fdwReason || dword_18004E120 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18004E124 = 1;
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
            if ( dword_18004E124 )
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
0x1800013c4  mov     [rsp+lpvReserved], r8
0x1800013c9  mov     [rsp+arg_8], edx
0x1800013cd  mov     [rsp+arg_0], rcx
0x1800013d2  push    rbx
0x1800013d3  push    rsi
0x1800013d4  push    rdi
0x1800013d5  sub     rsp, 0F0h
0x1800013dc  mov     edi, edx
0x1800013de  mov     rsi, rcx
0x1800013e1  mov     ebx, 1
0x1800013e6  cmp     edx, ebx
0x1800013e8  ja      short loc_1800013F0
0x1800013ea  mov     cs:__native_dllmain_reason, edx
0x1800013f0  test    edx, edx
0x1800013f2  jnz     short loc_180001407
0x1800013f4  cmp     cs:dword_18004E120, edx
0x1800013fa  jnz     short loc_180001407
0x1800013fc  xor     ebx, ebx
0x1800013fe  mov     [rsp+108h+var_E8], ebx
0x180001402  jmp     loc_1800015B4
0x180001407  lea     eax, [rdx-1]
0x18000140a  cmp     eax, 1
0x18000140d  ja      loc_180001494
0x180001413  mov     rax, cs:_pRawDllMain
0x18000141a  test    rax, rax
0x18000141d  jz      short loc_180001455
0x18000141f  cmp     edx, 1
0x180001422  jnz     short loc_18000142A
0x180001424  mov     cs:dword_18004E124, edx
0x18000142a  mov     r8, [rsp+108h+lpvReserved]
0x180001432  call    cs:__guard_dispatch_icall_fptr
0x180001438  mov     ebx, eax
0x18000143a  mov     [rsp+108h+var_E8], eax
0x18000143e  jmp     short loc_180001455
0x180001440  xor     ebx, ebx
0x180001442  mov     [rsp+108h+var_E8], ebx
0x180001446  mov     edi, [rsp+108h+arg_8]
0x18000144d  mov     rsi, [rsp+108h+arg_0]
0x180001455  test    ebx, ebx
0x180001457  jz      loc_1800015B4
0x18000145d  mov     r8, [rsp+108h+lpvReserved]
0x180001465  mov     edx, edi
0x180001467  mov     rcx, rsi
0x18000146a  call    _CRT_INIT
0x18000146f  mov     ebx, eax
0x180001471  mov     [rsp+108h+var_E8], eax
0x180001475  jmp     short loc_18000148C
0x180001477  xor     ebx, ebx
0x180001479  mov     [rsp+108h+var_E8], ebx
0x18000147d  mov     edi, [rsp+108h+arg_8]
0x180001484  mov     rsi, [rsp+108h+arg_0]
0x18000148c  test    ebx, ebx
0x18000148e  jz      loc_1800015B4
0x180001494  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000149c  mov     edx, edi; fdwReason
0x18000149e  mov     rcx, rsi; hinstDLL
0x1800014a1  call    DllMain
0x1800014a6  mov     ebx, eax
0x1800014a8  mov     [rsp+108h+var_E8], eax
0x1800014ac  jmp     short loc_1800014C3
0x1800014ae  xor     ebx, ebx
0x1800014b0  mov     [rsp+108h+var_E8], ebx
0x1800014b4  mov     edi, [rsp+108h+arg_8]
0x1800014bb  mov     rsi, [rsp+108h+arg_0]
0x1800014c3  cmp     edi, 1
0x1800014c6  jnz     short loc_18000153F
0x1800014c8  test    ebx, ebx
0x1800014ca  jnz     short loc_18000153F
0x1800014cc  xor     r8d, r8d; lpvReserved
0x1800014cf  xor     edx, edx; fdwReason
0x1800014d1  mov     rcx, rsi; hinstDLL
0x1800014d4  call    DllMain
0x1800014d9  jmp     short loc_1800014EE
0x1800014db  mov     edi, [rsp+108h+arg_8]
0x1800014e2  mov     rsi, [rsp+108h+arg_0]
0x1800014ea  mov     ebx, [rsp+108h+var_E8]
0x1800014ee  xor     r8d, r8d
0x1800014f1  xor     edx, edx
0x1800014f3  mov     rcx, rsi
0x1800014f6  call    _CRT_INIT
0x1800014fb  jmp     short loc_180001510
0x1800014fd  mov     edi, [rsp+108h+arg_8]
0x180001504  mov     rsi, [rsp+108h+arg_0]
0x18000150c  mov     ebx, [rsp+108h+var_E8]
0x180001510  mov     rax, cs:_pRawDllMain
0x180001517  test    rax, rax
0x18000151a  jz      short loc_18000153F
0x18000151c  xor     r8d, r8d
0x18000151f  xor     edx, edx
0x180001521  mov     rcx, rsi
0x180001524  call    cs:__guard_dispatch_icall_fptr
0x18000152a  jmp     short loc_18000153F
0x18000152c  mov     edi, [rsp+108h+arg_8]
0x180001533  mov     rsi, [rsp+108h+arg_0]
0x18000153b  mov     ebx, [rsp+108h+var_E8]
0x18000153f  test    edi, edi
0x180001541  jz      short loc_180001548
0x180001543  cmp     edi, 3
0x180001546  jnz     short loc_1800015B4
0x180001548  mov     r8, [rsp+108h+lpvReserved]
0x180001550  mov     edx, edi
0x180001552  mov     rcx, rsi
0x180001555  call    _CRT_INIT
0x18000155a  mov     ebx, eax
0x18000155c  mov     [rsp+108h+var_E8], eax
0x180001560  jmp     short loc_180001577
0x180001562  xor     ebx, ebx
0x180001564  mov     [rsp+108h+var_E8], ebx
0x180001568  mov     edi, [rsp+108h+arg_8]
0x18000156f  mov     rsi, [rsp+108h+arg_0]
0x180001577  mov     rax, cs:_pRawDllMain
0x18000157e  test    rax, rax
0x180001581  jz      short loc_1800015B4
0x180001583  cmp     cs:dword_18004E124, 0
0x18000158a  jz      short loc_1800015B4
0x18000158c  mov     r8, [rsp+108h+lpvReserved]
0x180001594  mov     edx, edi
0x180001596  mov     rcx, rsi
0x180001599  call    cs:__guard_dispatch_icall_fptr
0x18000159f  mov     ebx, eax
0x1800015a1  mov     [rsp+108h+var_E8], eax
0x1800015a5  jmp     short loc_1800015B4
0x1800015a7  xor     ebx, ebx
0x1800015a9  mov     [rsp+108h+var_E8], ebx
0x1800015ad  mov     edi, [rsp+108h+arg_8]
0x1800015b4  cmp     edi, 1
0x1800015b7  ja      short loc_1800015C3
0x1800015b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800015c3  mov     eax, ebx
0x1800015c5  add     rsp, 0F0h
0x1800015cc  pop     rdi
0x1800015cd  pop     rsi
0x1800015ce  pop     rbx
0x1800015cf  retn
0x18001d770  push    rbp
0x18001d772  sub     rsp, 20h
0x18001d776  mov     rbp, rdx
0x18001d779  mov     rax, [rcx]
0x18001d77c  mov     edx, [rax]
0x18001d77e  mov     [rbp+0A8h], rcx
0x18001d785  mov     [rbp+28h], edx
0x18001d788  mov     eax, [rbp+28h]
0x18001d78b  cmp     eax, 0E06D7363h
0x18001d790  jnz     short loc_18001D7A6
0x18001d792  mov     rdx, [rbp+0A8h]
0x18001d799  mov     ecx, [rbp+28h]
0x18001d79c  call    _XcptFilter_0
0x18001d7a1  mov     [rbp+30h], eax
0x18001d7a4  jmp     short loc_18001D7AD
0x18001d7a6  mov     dword ptr [rbp+30h], 0
0x18001d7ad  mov     eax, [rbp+30h]
0x18001d7b0  add     rsp, 20h
0x18001d7b4  pop     rbp
0x18001d7b5  retn
0x18001d7b7  push    rbp
0x18001d7b9  sub     rsp, 20h
0x18001d7bd  mov     rbp, rdx
0x18001d7c0  mov     rax, [rcx]
0x18001d7c3  mov     edx, [rax]
0x18001d7c5  mov     [rbp+0B0h], rcx
0x18001d7cc  mov     [rbp+38h], edx
0x18001d7cf  mov     eax, [rbp+38h]
0x18001d7d2  cmp     eax, 0E06D7363h
0x18001d7d7  jnz     short loc_18001D7ED
0x18001d7d9  mov     rdx, [rbp+0B0h]
0x18001d7e0  mov     ecx, [rbp+38h]
0x18001d7e3  call    _XcptFilter_0
0x18001d7e8  mov     [rbp+40h], eax
0x18001d7eb  jmp     short loc_18001D7F4
0x18001d7ed  mov     dword ptr [rbp+40h], 0
0x18001d7f4  mov     eax, [rbp+40h]
0x18001d7f7  add     rsp, 20h
0x18001d7fb  pop     rbp
0x18001d7fc  retn
0x18001d7fe  push    rbp
0x18001d800  sub     rsp, 20h
0x18001d804  mov     rbp, rdx
0x18001d807  mov     rax, [rcx]
0x18001d80a  mov     edx, [rax]
0x18001d80c  mov     [rbp+0B8h], rcx
0x18001d813  mov     [rbp+48h], edx
0x18001d816  mov     eax, [rbp+48h]
0x18001d819  cmp     eax, 0E06D7363h
0x18001d81e  jnz     short loc_18001D834
0x18001d820  mov     rdx, [rbp+0B8h]
0x18001d827  mov     ecx, [rbp+48h]
0x18001d82a  call    _XcptFilter_0
0x18001d82f  mov     [rbp+50h], eax
0x18001d832  jmp     short loc_18001D83B
0x18001d834  mov     dword ptr [rbp+50h], 0
0x18001d83b  mov     eax, [rbp+50h]
0x18001d83e  add     rsp, 20h
0x18001d842  pop     rbp
0x18001d843  retn
0x18001d845  push    rbp
0x18001d847  sub     rsp, 20h
0x18001d84b  mov     rbp, rdx
0x18001d84e  mov     rax, [rcx]
0x18001d851  mov     edx, [rax]
0x18001d853  mov     [rbp+0C0h], rcx
0x18001d85a  mov     [rbp+58h], edx
0x18001d85d  mov     eax, [rbp+58h]
0x18001d860  cmp     eax, 0E06D7363h
0x18001d865  jnz     short loc_18001D87B
0x18001d867  mov     rdx, [rbp+0C0h]
0x18001d86e  mov     ecx, [rbp+58h]
0x18001d871  call    _XcptFilter_0
0x18001d876  mov     [rbp+60h], eax
0x18001d879  jmp     short loc_18001D882
0x18001d87b  mov     dword ptr [rbp+60h], 0
0x18001d882  mov     eax, [rbp+60h]
0x18001d885  add     rsp, 20h
0x18001d889  pop     rbp
0x18001d88a  retn
0x18001d88c  push    rbp
0x18001d88e  sub     rsp, 20h
0x18001d892  mov     rbp, rdx
0x18001d895  mov     rax, [rcx]
0x18001d898  mov     edx, [rax]
0x18001d89a  mov     [rbp+0C8h], rcx
0x18001d8a1  mov     [rbp+68h], edx
0x18001d8a4  mov     eax, [rbp+68h]
0x18001d8a7  cmp     eax, 0E06D7363h
0x18001d8ac  jnz     short loc_18001D8C2
0x18001d8ae  mov     rdx, [rbp+0C8h]
0x18001d8b5  mov     ecx, [rbp+68h]
0x18001d8b8  call    _XcptFilter_0
0x18001d8bd  mov     [rbp+70h], eax
0x18001d8c0  jmp     short loc_18001D8C9
0x18001d8c2  mov     dword ptr [rbp+70h], 0
0x18001d8c9  mov     eax, [rbp+70h]
0x18001d8cc  add     rsp, 20h
0x18001d8d0  pop     rbp
0x18001d8d1  retn
0x18001d8d3  push    rbp
0x18001d8d5  sub     rsp, 20h
0x18001d8d9  mov     rbp, rdx
0x18001d8dc  mov     rax, [rcx]
0x18001d8df  mov     edx, [rax]
0x18001d8e1  mov     [rbp+0D0h], rcx
0x18001d8e8  mov     [rbp+78h], edx
0x18001d8eb  mov     eax, [rbp+78h]
0x18001d8ee  cmp     eax, 0E06D7363h
0x18001d8f3  jnz     short loc_18001D90C
0x18001d8f5  mov     rdx, [rbp+0D0h]
0x18001d8fc  mov     ecx, [rbp+78h]
0x18001d8ff  call    _XcptFilter_0
0x18001d904  mov     [rbp+80h], eax
0x18001d90a  jmp     short loc_18001D916
0x18001d90c  mov     dword ptr [rbp+80h], 0
0x18001d916  mov     eax, [rbp+80h]
0x18001d91c  add     rsp, 20h
0x18001d920  pop     rbp
0x18001d921  retn
0x18001d923  push    rbp
0x18001d925  sub     rsp, 20h
0x18001d929  mov     rbp, rdx
0x18001d92c  mov     rax, [rcx]
0x18001d92f  mov     edx, [rax]
0x18001d931  mov     [rbp+0D8h], rcx
0x18001d938  mov     [rbp+88h], edx
0x18001d93e  mov     eax, [rbp+88h]
0x18001d944  cmp     eax, 0E06D7363h
0x18001d949  jnz     short loc_18001D965
0x18001d94b  mov     rdx, [rbp+0D8h]
0x18001d952  mov     ecx, [rbp+88h]
0x18001d958  call    _XcptFilter_0
0x18001d95d  mov     [rbp+90h], eax
0x18001d963  jmp     short loc_18001D96F
0x18001d965  mov     dword ptr [rbp+90h], 0
0x18001d96f  mov     eax, [rbp+90h]
0x18001d975  add     rsp, 20h
0x18001d979  pop     rbp
0x18001d97a  retn
0x18001d97c  push    rbp
0x18001d97e  sub     rsp, 20h
0x18001d982  mov     rbp, rdx
0x18001d985  mov     rax, [rcx]
0x18001d988  mov     edx, [rax]
0x18001d98a  mov     [rbp+0E0h], rcx
0x18001d991  mov     [rbp+98h], edx
0x18001d997  mov     eax, [rbp+98h]
0x18001d99d  cmp     eax, 0E06D7363h
0x18001d9a2  jnz     short loc_18001D9BE
0x18001d9a4  mov     rdx, [rbp+0E0h]
0x18001d9ab  mov     ecx, [rbp+98h]
0x18001d9b1  call    _XcptFilter_0
0x18001d9b6  mov     [rbp+0A0h], eax
0x18001d9bc  jmp     short loc_18001D9C8
0x18001d9be  mov     dword ptr [rbp+0A0h], 0
0x18001d9c8  mov     eax, [rbp+0A0h]
0x18001d9ce  add     rsp, 20h
0x18001d9d2  pop     rbp
0x18001d9d3  retn
0x18001d9d5  push    rbp
0x18001d9d7  sub     rsp, 20h
0x18001d9db  mov     rbp, rdx
0x18001d9de  cmp     dword ptr [rbp+118h], 1
0x18001d9e5  ja      short loc_18001D9F1
0x18001d9e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
