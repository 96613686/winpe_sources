# ManageCI_GetPolicyInformation

- ea: `0x180008fb0`
- end: `0x1800090c9`
- name: `ManageCI_GetPolicyInformation`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800052c0`
- `0x180007678`
- `0x18000769c`
- `0x18000828c`
- `0x1800086b4`
- `0x180008fb0`
- `0x180012da0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180009072`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180009072`

## string_xrefs

- `0x180009093`: `onecore\base\ci\management\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall ManageCI_GetPolicyInformation(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  CodeIntegrity::Management::SiPolicyView *v10; // r10
  unsigned __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  const char *v14; // r9
  __int64 result; // rax
  __int64 v16; // rax
  __int64 v17; // r10
  __int64 v18; // r9
  unsigned int v19; // ebx
  CodeIntegrity::Management::SiPolicyView *v20[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    CodeIntegrity::Management::GetPolicyInformation(v20, a1);
    v10 = v20[0];
    v11 = 2LL * *((_QWORD *)v20[0] + 5) + 34;
    if ( v11 > 0xFFFFFFFF )
    {
      *a4 = -1;
      v19 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x157,
              (unsigned int)"onecore\\base\\ci\\management\\dll\\dllmain.cpp",
              (const char *)0xC0000095LL,
              (int)v20[0]);
      std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(v20);
      result = v19;
    }
    else
    {
      *a4 = v11;
      if ( a3 >= (unsigned int)v11 )
      {
        if ( a2 )
        {
          *(_QWORD *)a2 = *((_QWORD *)v10 + 2);
          *(_BYTE *)(a2 + 8) = *((_BYTE *)v10 + 88);
          *(_BYTE *)(a2 + 9) = *((_BYTE *)v10 + 90);
          *(_BYTE *)(a2 + 10) = CodeIntegrity::Management::SiPolicyView::is_authorized(v10);
          *(_DWORD *)(a2 + 24) = 0;
          *(_QWORD *)(a2 + 16) = a2 + 32;
          v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          _o_wcscpy_s(v18, *(_QWORD *)(v17 + 40) + 1LL, v16);
        }
        std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(v20);
        result = 0;
      }
      else
      {
        v12 = wil::details::in1diag3::Return_Win32(retaddr, v7, v8, v9, (unsigned int)v20[0]);
        std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(v20);
        result = v12;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x16E, v13, v14);
  }
  return result;
}

```

## disassembly

```asm
0x180008fb0  mov     [rsp+arg_0], rbx
0x180008fb5  mov     [rsp+arg_8], rsi
0x180008fba  push    rdi
0x180008fbb  sub     rsp, 30h
0x180008fbf  mov     rdi, r9
0x180008fc2  mov     esi, r8d
0x180008fc5  mov     rbx, rdx
0x180008fc8  mov     rdx, rcx
0x180008fcb  lea     rcx, [rsp+38h+var_18]
0x180008fd0  call    ?GetPolicyInformation@Management@CodeIntegrity@@YA?AV?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@PEBU_GUID@@@Z; CodeIntegrity::Management::GetPolicyInformation(_GUID const *)
0x180008fd5  mov     r10, [rsp+38h+var_18]
0x180008fda  mov     rax, [r10+28h]
0x180008fde  lea     rax, ds:22h[rax*2]
0x180008fe6  mov     ecx, 0FFFFFFFFh
0x180008feb  cmp     rax, rcx
0x180008fee  ja      loc_180009086
0x180008ff4  mov     [rdi], eax
0x180008ff6  cmp     esi, eax
0x180008ff8  jnb     short loc_180009017
0x180008ffa  mov     rcx, [rsp+38h]; this
0x180008fff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009004  mov     ebx, eax
0x180009006  lea     rcx, [rsp+38h+var_18]
0x18000900b  call    ??1?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAA@XZ; std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(void)
0x180009010  mov     eax, ebx
0x180009012  jmp     loc_1800090B8
0x180009017  test    rbx, rbx
0x18000901a  jnz     short loc_18000902D
0x18000901c  lea     rcx, [rsp+38h+var_18]
0x180009021  call    ??1?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAA@XZ; std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(void)
0x180009026  xor     eax, eax
0x180009028  jmp     loc_1800090B8
0x18000902d  mov     rax, [r10+10h]
0x180009031  mov     [rbx], rax
0x180009034  mov     al, [r10+58h]
0x180009038  mov     [rbx+8], al
0x18000903b  mov     al, [r10+5Ah]
0x18000903f  mov     [rbx+9], al
0x180009042  mov     rcx, r10; this
0x180009045  call    ?is_authorized@SiPolicyView@Management@CodeIntegrity@@QEBA_NXZ; CodeIntegrity::Management::SiPolicyView::is_authorized(void)
0x18000904a  mov     [rbx+0Ah], al
0x18000904d  mov     dword ptr [rbx+18h], 0
0x180009054  lea     r9, [rbx+20h]
0x180009058  mov     [rbx+10h], r9
0x18000905c  lea     rcx, [r10+18h]
0x180009060  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180009065  mov     rdx, [r10+28h]
0x180009069  inc     rdx
0x18000906c  mov     r8, rax
0x18000906f  mov     rcx, r9
0x180009072  call    cs:__imp__o_wcscpy_s
0x180009078  lea     rcx, [rsp+38h+var_18]
0x18000907d  call    ??1?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAA@XZ; std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(void)
0x180009082  xor     eax, eax
0x180009084  jmp     short loc_1800090B8
0x180009086  mov     [rdi], ecx
0x180009088  mov     rcx, [rsp+38h]; this
0x18000908d  mov     r9d, 0C0000095h; char *
0x180009093  lea     r8, aOnecoreBaseCiM; "onecore\\base\\ci\\management\\dll\\dll"...
0x18000909a  mov     edx, 157h; void *
0x18000909f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800090a4  mov     ebx, eax
0x1800090a6  lea     rcx, [rsp+38h+var_18]
0x1800090ab  call    ??1?$unique_ptr@$$CBVSiPolicyView@Management@CodeIntegrity@@U?$default_delete@$$CBVSiPolicyView@Management@CodeIntegrity@@@std@@@std@@QEAA@XZ; std::unique_ptr<CodeIntegrity::Management::SiPolicyView const>::~unique_ptr<CodeIntegrity::Management::SiPolicyView const>(void)
0x1800090b0  mov     eax, ebx
0x1800090b2  jmp     short loc_1800090B8
0x1800090b4  mov     eax, dword ptr [rsp+38h+var_18]
0x1800090b8  mov     rbx, [rsp+38h+arg_0]
0x1800090bd  mov     rsi, [rsp+38h+arg_8]
0x1800090c2  add     rsp, 30h
0x1800090c6  pop     rdi
0x1800090c7  retn
```
