# __DllMainCRTStartup

- ea: `0x180001824`
- end: `0x180001a30`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800017e0`

## callees

- `0x1800015b0`
- `0x180001824`
- `0x180001d61`
- `0x180012e4c`
- `0x180013740`

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
  if ( (_DWORD)fdwReason || dword_18001E440 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18001E444 = 1;
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
            if ( dword_18001E444 )
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
0x180001824  mov     [rsp+lpvReserved], r8
0x180001829  mov     [rsp+arg_8], edx
0x18000182d  mov     [rsp+arg_0], rcx
0x180001832  push    rbx
0x180001833  push    rsi
0x180001834  push    rdi
0x180001835  sub     rsp, 0F0h
0x18000183c  mov     edi, edx
0x18000183e  mov     rsi, rcx
0x180001841  mov     ebx, 1
0x180001846  cmp     edx, ebx
0x180001848  ja      short loc_180001850
0x18000184a  mov     cs:__native_dllmain_reason, edx
0x180001850  test    edx, edx
0x180001852  jnz     short loc_180001867
0x180001854  cmp     cs:dword_18001E440, edx
0x18000185a  jnz     short loc_180001867
0x18000185c  xor     ebx, ebx
0x18000185e  mov     [rsp+108h+var_E8], ebx
0x180001862  jmp     loc_180001A14
0x180001867  lea     eax, [rdx-1]
0x18000186a  cmp     eax, 1
0x18000186d  ja      loc_1800018F4
0x180001873  mov     rax, cs:_pRawDllMain
0x18000187a  test    rax, rax
0x18000187d  jz      short loc_1800018B5
0x18000187f  cmp     edx, 1
0x180001882  jnz     short loc_18000188A
0x180001884  mov     cs:dword_18001E444, edx
0x18000188a  mov     r8, [rsp+108h+lpvReserved]
0x180001892  call    cs:__guard_dispatch_icall_fptr
0x180001898  mov     ebx, eax
0x18000189a  mov     [rsp+108h+var_E8], eax
0x18000189e  jmp     short loc_1800018B5
0x1800018a0  xor     ebx, ebx
0x1800018a2  mov     [rsp+108h+var_E8], ebx
0x1800018a6  mov     edi, [rsp+108h+arg_8]
0x1800018ad  mov     rsi, [rsp+108h+arg_0]
0x1800018b5  test    ebx, ebx
0x1800018b7  jz      loc_180001A14
0x1800018bd  mov     r8, [rsp+108h+lpvReserved]
0x1800018c5  mov     edx, edi
0x1800018c7  mov     rcx, rsi
0x1800018ca  call    _CRT_INIT
0x1800018cf  mov     ebx, eax
0x1800018d1  mov     [rsp+108h+var_E8], eax
0x1800018d5  jmp     short loc_1800018EC
0x1800018d7  xor     ebx, ebx
0x1800018d9  mov     [rsp+108h+var_E8], ebx
0x1800018dd  mov     edi, [rsp+108h+arg_8]
0x1800018e4  mov     rsi, [rsp+108h+arg_0]
0x1800018ec  test    ebx, ebx
0x1800018ee  jz      loc_180001A14
0x1800018f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800018fc  mov     edx, edi; fdwReason
0x1800018fe  mov     rcx, rsi; hinstDLL
0x180001901  call    DllMain
0x180001906  mov     ebx, eax
0x180001908  mov     [rsp+108h+var_E8], eax
0x18000190c  jmp     short loc_180001923
0x18000190e  xor     ebx, ebx
0x180001910  mov     [rsp+108h+var_E8], ebx
0x180001914  mov     edi, [rsp+108h+arg_8]
0x18000191b  mov     rsi, [rsp+108h+arg_0]
0x180001923  cmp     edi, 1
0x180001926  jnz     short loc_18000199F
0x180001928  test    ebx, ebx
0x18000192a  jnz     short loc_18000199F
0x18000192c  xor     r8d, r8d; lpvReserved
0x18000192f  xor     edx, edx; fdwReason
0x180001931  mov     rcx, rsi; hinstDLL
0x180001934  call    DllMain
0x180001939  jmp     short loc_18000194E
0x18000193b  mov     edi, [rsp+108h+arg_8]
0x180001942  mov     rsi, [rsp+108h+arg_0]
0x18000194a  mov     ebx, [rsp+108h+var_E8]
0x18000194e  xor     r8d, r8d
0x180001951  xor     edx, edx
0x180001953  mov     rcx, rsi
0x180001956  call    _CRT_INIT
0x18000195b  jmp     short loc_180001970
0x18000195d  mov     edi, [rsp+108h+arg_8]
0x180001964  mov     rsi, [rsp+108h+arg_0]
0x18000196c  mov     ebx, [rsp+108h+var_E8]
0x180001970  mov     rax, cs:_pRawDllMain
0x180001977  test    rax, rax
0x18000197a  jz      short loc_18000199F
0x18000197c  xor     r8d, r8d
0x18000197f  xor     edx, edx
0x180001981  mov     rcx, rsi
0x180001984  call    cs:__guard_dispatch_icall_fptr
0x18000198a  jmp     short loc_18000199F
0x18000198c  mov     edi, [rsp+108h+arg_8]
0x180001993  mov     rsi, [rsp+108h+arg_0]
0x18000199b  mov     ebx, [rsp+108h+var_E8]
0x18000199f  test    edi, edi
0x1800019a1  jz      short loc_1800019A8
0x1800019a3  cmp     edi, 3
0x1800019a6  jnz     short loc_180001A14
0x1800019a8  mov     r8, [rsp+108h+lpvReserved]
0x1800019b0  mov     edx, edi
0x1800019b2  mov     rcx, rsi
0x1800019b5  call    _CRT_INIT
0x1800019ba  mov     ebx, eax
0x1800019bc  mov     [rsp+108h+var_E8], eax
0x1800019c0  jmp     short loc_1800019D7
0x1800019c2  xor     ebx, ebx
0x1800019c4  mov     [rsp+108h+var_E8], ebx
0x1800019c8  mov     edi, [rsp+108h+arg_8]
0x1800019cf  mov     rsi, [rsp+108h+arg_0]
0x1800019d7  mov     rax, cs:_pRawDllMain
0x1800019de  test    rax, rax
0x1800019e1  jz      short loc_180001A14
0x1800019e3  cmp     cs:dword_18001E444, 0
0x1800019ea  jz      short loc_180001A14
0x1800019ec  mov     r8, [rsp+108h+lpvReserved]
0x1800019f4  mov     edx, edi
0x1800019f6  mov     rcx, rsi
0x1800019f9  call    cs:__guard_dispatch_icall_fptr
0x1800019ff  mov     ebx, eax
0x180001a01  mov     [rsp+108h+var_E8], eax
0x180001a05  jmp     short loc_180001A14
0x180001a07  xor     ebx, ebx
0x180001a09  mov     [rsp+108h+var_E8], ebx
0x180001a0d  mov     edi, [rsp+108h+arg_8]
0x180001a14  cmp     edi, 1
0x180001a17  ja      short loc_180001A23
0x180001a19  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001a23  mov     eax, ebx
0x180001a25  add     rsp, 0F0h
0x180001a2c  pop     rdi
0x180001a2d  pop     rsi
0x180001a2e  pop     rbx
0x180001a2f  retn
0x1800137b0  push    rbp
0x1800137b2  sub     rsp, 20h
0x1800137b6  mov     rbp, rdx
0x1800137b9  mov     rax, [rcx]
0x1800137bc  mov     edx, [rax]
0x1800137be  mov     [rbp+0A8h], rcx
0x1800137c5  mov     [rbp+28h], edx
0x1800137c8  mov     eax, [rbp+28h]
0x1800137cb  cmp     eax, 0E06D7363h
0x1800137d0  jnz     short loc_1800137E6
0x1800137d2  mov     rdx, [rbp+0A8h]
0x1800137d9  mov     ecx, [rbp+28h]
0x1800137dc  call    _XcptFilter_0
0x1800137e1  mov     [rbp+30h], eax
0x1800137e4  jmp     short loc_1800137ED
0x1800137e6  mov     dword ptr [rbp+30h], 0
0x1800137ed  mov     eax, [rbp+30h]
0x1800137f0  add     rsp, 20h
0x1800137f4  pop     rbp
0x1800137f5  retn
0x1800137f7  push    rbp
0x1800137f9  sub     rsp, 20h
0x1800137fd  mov     rbp, rdx
0x180013800  mov     rax, [rcx]
0x180013803  mov     edx, [rax]
0x180013805  mov     [rbp+0B0h], rcx
0x18001380c  mov     [rbp+38h], edx
0x18001380f  mov     eax, [rbp+38h]
0x180013812  cmp     eax, 0E06D7363h
0x180013817  jnz     short loc_18001382D
0x180013819  mov     rdx, [rbp+0B0h]
0x180013820  mov     ecx, [rbp+38h]
0x180013823  call    _XcptFilter_0
0x180013828  mov     [rbp+40h], eax
0x18001382b  jmp     short loc_180013834
0x18001382d  mov     dword ptr [rbp+40h], 0
0x180013834  mov     eax, [rbp+40h]
0x180013837  add     rsp, 20h
0x18001383b  pop     rbp
0x18001383c  retn
0x18001383e  push    rbp
0x180013840  sub     rsp, 20h
0x180013844  mov     rbp, rdx
0x180013847  mov     rax, [rcx]
0x18001384a  mov     edx, [rax]
0x18001384c  mov     [rbp+0B8h], rcx
0x180013853  mov     [rbp+48h], edx
0x180013856  mov     eax, [rbp+48h]
0x180013859  cmp     eax, 0E06D7363h
0x18001385e  jnz     short loc_180013874
0x180013860  mov     rdx, [rbp+0B8h]
0x180013867  mov     ecx, [rbp+48h]
0x18001386a  call    _XcptFilter_0
0x18001386f  mov     [rbp+50h], eax
0x180013872  jmp     short loc_18001387B
0x180013874  mov     dword ptr [rbp+50h], 0
0x18001387b  mov     eax, [rbp+50h]
0x18001387e  add     rsp, 20h
0x180013882  pop     rbp
0x180013883  retn
0x180013885  push    rbp
0x180013887  sub     rsp, 20h
0x18001388b  mov     rbp, rdx
0x18001388e  mov     rax, [rcx]
0x180013891  mov     edx, [rax]
0x180013893  mov     [rbp+0C0h], rcx
0x18001389a  mov     [rbp+58h], edx
0x18001389d  mov     eax, [rbp+58h]
0x1800138a0  cmp     eax, 0E06D7363h
0x1800138a5  jnz     short loc_1800138BB
0x1800138a7  mov     rdx, [rbp+0C0h]
0x1800138ae  mov     ecx, [rbp+58h]
0x1800138b1  call    _XcptFilter_0
0x1800138b6  mov     [rbp+60h], eax
0x1800138b9  jmp     short loc_1800138C2
0x1800138bb  mov     dword ptr [rbp+60h], 0
0x1800138c2  mov     eax, [rbp+60h]
0x1800138c5  add     rsp, 20h
0x1800138c9  pop     rbp
0x1800138ca  retn
0x1800138cc  push    rbp
0x1800138ce  sub     rsp, 20h
0x1800138d2  mov     rbp, rdx
0x1800138d5  mov     rax, [rcx]
0x1800138d8  mov     edx, [rax]
0x1800138da  mov     [rbp+0C8h], rcx
0x1800138e1  mov     [rbp+68h], edx
0x1800138e4  mov     eax, [rbp+68h]
0x1800138e7  cmp     eax, 0E06D7363h
0x1800138ec  jnz     short loc_180013902
0x1800138ee  mov     rdx, [rbp+0C8h]
0x1800138f5  mov     ecx, [rbp+68h]
0x1800138f8  call    _XcptFilter_0
0x1800138fd  mov     [rbp+70h], eax
0x180013900  jmp     short loc_180013909
0x180013902  mov     dword ptr [rbp+70h], 0
0x180013909  mov     eax, [rbp+70h]
0x18001390c  add     rsp, 20h
0x180013910  pop     rbp
0x180013911  retn
0x180013913  push    rbp
0x180013915  sub     rsp, 20h
0x180013919  mov     rbp, rdx
0x18001391c  mov     rax, [rcx]
0x18001391f  mov     edx, [rax]
0x180013921  mov     [rbp+0D0h], rcx
0x180013928  mov     [rbp+78h], edx
0x18001392b  mov     eax, [rbp+78h]
0x18001392e  cmp     eax, 0E06D7363h
0x180013933  jnz     short loc_18001394C
0x180013935  mov     rdx, [rbp+0D0h]
0x18001393c  mov     ecx, [rbp+78h]
0x18001393f  call    _XcptFilter_0
0x180013944  mov     [rbp+80h], eax
0x18001394a  jmp     short loc_180013956
0x18001394c  mov     dword ptr [rbp+80h], 0
0x180013956  mov     eax, [rbp+80h]
0x18001395c  add     rsp, 20h
0x180013960  pop     rbp
0x180013961  retn
0x180013963  push    rbp
0x180013965  sub     rsp, 20h
0x180013969  mov     rbp, rdx
0x18001396c  mov     rax, [rcx]
0x18001396f  mov     edx, [rax]
0x180013971  mov     [rbp+0D8h], rcx
0x180013978  mov     [rbp+88h], edx
0x18001397e  mov     eax, [rbp+88h]
0x180013984  cmp     eax, 0E06D7363h
0x180013989  jnz     short loc_1800139A5
0x18001398b  mov     rdx, [rbp+0D8h]
0x180013992  mov     ecx, [rbp+88h]
0x180013998  call    _XcptFilter_0
0x18001399d  mov     [rbp+90h], eax
0x1800139a3  jmp     short loc_1800139AF
0x1800139a5  mov     dword ptr [rbp+90h], 0
0x1800139af  mov     eax, [rbp+90h]
0x1800139b5  add     rsp, 20h
0x1800139b9  pop     rbp
0x1800139ba  retn
0x1800139bc  push    rbp
0x1800139be  sub     rsp, 20h
0x1800139c2  mov     rbp, rdx
0x1800139c5  mov     rax, [rcx]
0x1800139c8  mov     edx, [rax]
0x1800139ca  mov     [rbp+0E0h], rcx
0x1800139d1  mov     [rbp+98h], edx
0x1800139d7  mov     eax, [rbp+98h]
0x1800139dd  cmp     eax, 0E06D7363h
0x1800139e2  jnz     short loc_1800139FE
0x1800139e4  mov     rdx, [rbp+0E0h]
0x1800139eb  mov     ecx, [rbp+98h]
0x1800139f1  call    _XcptFilter_0
0x1800139f6  mov     [rbp+0A0h], eax
0x1800139fc  jmp     short loc_180013A08
0x1800139fe  mov     dword ptr [rbp+0A0h], 0
0x180013a08  mov     eax, [rbp+0A0h]
0x180013a0e  add     rsp, 20h
0x180013a12  pop     rbp
0x180013a13  retn
0x180013a15  push    rbp
0x180013a17  sub     rsp, 20h
0x180013a1b  mov     rbp, rdx
0x180013a1e  cmp     dword ptr [rbp+118h], 1
0x180013a25  ja      short loc_180013A31
0x180013a27  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
