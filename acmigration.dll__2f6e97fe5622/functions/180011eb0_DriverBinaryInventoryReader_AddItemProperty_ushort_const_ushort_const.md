# DriverBinaryInventoryReader::AddItemProperty(ushort const *,ushort const *)

- ea: `0x180011eb0`
- end: `0x1800120a9`
- name: `?AddItemProperty@DriverBinaryInventoryReader@@UEAAJPEBG0@Z`
- size: `505`
- prototype: `int(DriverBinaryInventoryReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18000c190`
- `0x180011dbc`
- `0x180011eb0`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011eee`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f0d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011ff8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011eee`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f0d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011ff8`

## string_xrefs

- `0x180011f31`: `Service`
- `0x180011fcb`: `Driver service name is: %ws`
- `0x180011fdd`: `DriverBinaryInventoryReader::AddItemProperty`
- `0x180012085`: `DriverBinaryInventoryReader::AddItemProperty`

## pseudocode

```c
__int64 __fastcall DriverBinaryInventoryReader::AddItemProperty(
        DriverBinaryInventoryReader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  _QWORD *v6; // rcx
  unsigned __int64 v7; // r14
  char **v8; // rdi
  unsigned __int64 v9; // rdx
  char *v10; // r15
  __int64 v11; // rbx
  __int64 v12; // rax
  _WORD *v13; // rcx
  char *v14; // rax
  __int64 v15; // rax
  void *v16; // r15

  if ( *((_BYTE *)this + 8) && !*((_BYTE *)this + 11) )
  {
    if ( *((_BYTE *)this + 9) || (unsigned int)_o__wcsicmp(L"DriverName", a2) )
    {
      if ( *((_BYTE *)this + 10) )
      {
        v7 = -1;
        v8 = (char **)((char *)this + 48);
        if ( !(unsigned int)_o__wcsicmp(L"Service", a2) )
        {
          v9 = -1;
          do
            ++v9;
          while ( a3[v9] );
          if ( v9 > *((_QWORD *)this + 9) )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)this + 48);
          }
          else
          {
            if ( *((_QWORD *)this + 9) <= 7u )
              v10 = (char *)this + 48;
            else
              v10 = *v8;
            v11 = 2 * v9;
            *((_QWORD *)this + 8) = v9;
            memmove_0(v10, a3, 2 * v9);
            *(_WORD *)&v10[v11] = 0;
          }
          v12 = std::map<std::wstring,std::wstring>::operator[]((char *)this + 80, (char *)this + 48);
          if ( *(_QWORD *)(v12 + 24) <= 7u )
            v13 = (_WORD *)v12;
          else
            v13 = *(_WORD **)v12;
          *(_QWORD *)(v12 + 16) = 0;
          *v13 = 0;
          if ( *((_QWORD *)this + 9) <= 7u )
            v14 = (char *)this + 48;
          else
            v14 = *v8;
          AslLogCallPrintf(3, "DriverBinaryInventoryReader::AddItemProperty", 250, "Driver service name is: %ws", v14);
        }
        if ( !(unsigned int)_o__wcsicmp(L"DriverCheckSum", a2) )
        {
          v15 = std::map<std::wstring,std::wstring>::operator[]((char *)this + 80, (char *)this + 48);
          do
            ++v7;
          while ( a3[v7] );
          if ( v7 > *(_QWORD *)(v15 + 24) )
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v15);
          }
          else
          {
            if ( *(_QWORD *)(v15 + 24) <= 7u )
              v16 = (void *)v15;
            else
              v16 = *(void **)v15;
            *(_QWORD *)(v15 + 16) = v7;
            memmove_0(v16, a3, 2 * v7);
            *((_WORD *)v16 + v7) = 0;
          }
          *((_BYTE *)this + 11) = 1;
          *((_QWORD *)this + 8) = 0;
          if ( *((_QWORD *)this + 9) > 7u )
            v8 = (char **)*v8;
          *(_WORD *)v8 = 0;
          AslLogCallPrintf(3, "DriverBinaryInventoryReader::AddItemProperty", 258, "Driver checksum is: %ws", a3);
        }
      }
    }
    else
    {
      v6 = (_QWORD *)((char *)this + 16);
      *((_BYTE *)this + 9) = 1;
      if ( *((_QWORD *)this + 5) > 7u )
        v6 = (_QWORD *)*v6;
      if ( !(unsigned int)_o__wcsicmp(v6, a3) )
        *((_BYTE *)this + 10) = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011eb0  push    rbx
0x180011eb2  push    rbp
0x180011eb3  push    rsi
0x180011eb4  push    rdi
0x180011eb5  push    r12
0x180011eb7  push    r13
0x180011eb9  push    r14
0x180011ebb  push    r15
0x180011ebd  sub     rsp, 38h
0x180011ec1  xor     r13d, r13d
0x180011ec4  mov     rbp, r8
0x180011ec7  mov     r12, rdx
0x180011eca  mov     rsi, rcx
0x180011ecd  cmp     [rcx+8], r13b
0x180011ed1  jz      loc_180012096
0x180011ed7  cmp     [rcx+0Bh], r13b
0x180011edb  jnz     loc_180012096
0x180011ee1  cmp     [rcx+9], r13b
0x180011ee5  jnz     short loc_180011F24
0x180011ee7  lea     rcx, aDrivername; "DriverName"
0x180011eee  call    cs:__imp__o__wcsicmp
0x180011ef4  test    eax, eax
0x180011ef6  jnz     short loc_180011F24
0x180011ef8  lea     rcx, [rsi+10h]
0x180011efc  mov     byte ptr [rsi+9], 1
0x180011f00  cmp     qword ptr [rcx+18h], 7
0x180011f05  jbe     short loc_180011F0A
0x180011f07  mov     rcx, [rcx]
0x180011f0a  mov     rdx, rbp
0x180011f0d  call    cs:__imp__o__wcsicmp
0x180011f13  test    eax, eax
0x180011f15  jnz     loc_180012096
0x180011f1b  mov     byte ptr [rsi+0Ah], 1
0x180011f1f  jmp     loc_180012096
0x180011f24  cmp     [rsi+0Ah], r13b
0x180011f28  jz      loc_180012096
0x180011f2e  mov     rdx, r12
0x180011f31  lea     rcx, aService; "Service"
0x180011f38  call    cs:__imp__o__wcsicmp
0x180011f3e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011f42  lea     rdi, [rsi+30h]
0x180011f46  test    eax, eax
0x180011f48  jnz     loc_180011FEE
0x180011f4e  mov     rdx, r14
0x180011f51  inc     rdx
0x180011f54  cmp     [rbp+rdx*2+0], r13w
0x180011f5a  jnz     short loc_180011F51
0x180011f5c  cmp     rdx, [rdi+18h]
0x180011f60  ja      short loc_180011F8E
0x180011f62  cmp     qword ptr [rdi+18h], 7
0x180011f67  jbe     short loc_180011F6E
0x180011f69  mov     r15, [rdi]
0x180011f6c  jmp     short loc_180011F71
0x180011f6e  mov     r15, rdi
0x180011f71  lea     rbx, [rdx+rdx]
0x180011f75  mov     [rdi+10h], rdx
0x180011f79  mov     r8, rbx; Size
0x180011f7c  mov     rdx, rbp; Src
0x180011f7f  mov     rcx, r15; void *
0x180011f82  call    memmove_0
0x180011f87  mov     [rbx+r15], r13w
0x180011f8c  jmp     short loc_180011F99
0x180011f8e  mov     r9, rbp
0x180011f91  mov     rcx, rdi
0x180011f94  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180011f99  lea     rcx, [rsi+50h]
0x180011f9d  mov     rdx, rdi
0x180011fa0  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x180011fa5  cmp     qword ptr [rax+18h], 7
0x180011faa  jbe     short loc_180011FB1
0x180011fac  mov     rcx, [rax]
0x180011faf  jmp     short loc_180011FB4
0x180011fb1  mov     rcx, rax
0x180011fb4  mov     [rax+10h], r13
0x180011fb8  mov     [rcx], r13w
0x180011fbc  cmp     qword ptr [rdi+18h], 7
0x180011fc1  jbe     short loc_180011FC8
0x180011fc3  mov     rax, [rdi]
0x180011fc6  jmp     short loc_180011FCB
0x180011fc8  mov     rax, rdi
0x180011fcb  lea     r9, aDriverServiceN; "Driver service name is: %ws"
0x180011fd2  mov     [rsp+78h+var_58], rax
0x180011fd7  mov     r8d, 0FAh
0x180011fdd  lea     rdx, aDriverbinaryin; "DriverBinaryInventoryReader::AddItemPro"...
0x180011fe4  mov     ecx, 3
0x180011fe9  call    AslLogCallPrintf
0x180011fee  mov     rdx, r12
0x180011ff1  lea     rcx, aDriverchecksum; "DriverCheckSum"
0x180011ff8  call    cs:__imp__o__wcsicmp
0x180011ffe  test    eax, eax
0x180012000  jnz     loc_180012096
0x180012006  lea     rcx, [rsi+50h]
0x18001200a  mov     rdx, rdi
0x18001200d  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring const &)
0x180012012  inc     r14
0x180012015  cmp     [rbp+r14*2+0], r13w
0x18001201b  jnz     short loc_180012012
0x18001201d  cmp     r14, [rax+18h]
0x180012021  ja      short loc_18001204F
0x180012023  cmp     qword ptr [rax+18h], 7
0x180012028  jbe     short loc_18001202F
0x18001202a  mov     r15, [rax]
0x18001202d  jmp     short loc_180012032
0x18001202f  mov     r15, rax
0x180012032  lea     rbx, [r14+r14]
0x180012036  mov     [rax+10h], r14
0x18001203a  mov     r8, rbx; Size
0x18001203d  mov     rdx, rbp; Src
0x180012040  mov     rcx, r15; void *
0x180012043  call    memmove_0
0x180012048  mov     [rbx+r15], r13w
0x18001204d  jmp     short loc_18001205D
0x18001204f  mov     r9, rbp
0x180012052  mov     rdx, r14
0x180012055  mov     rcx, rax
0x180012058  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001205d  mov     byte ptr [rsi+0Bh], 1
0x180012061  mov     [rdi+10h], r13
0x180012065  cmp     qword ptr [rdi+18h], 7
0x18001206a  jbe     short loc_18001206F
0x18001206c  mov     rdi, [rdi]
0x18001206f  lea     r9, aDriverChecksum; "Driver checksum is: %ws"
0x180012076  mov     [rdi], r13w
0x18001207a  mov     r8d, 102h
0x180012080  mov     [rsp+78h+var_58], rbp
0x180012085  lea     rdx, aDriverbinaryin; "DriverBinaryInventoryReader::AddItemPro"...
0x18001208c  mov     ecx, 3
0x180012091  call    AslLogCallPrintf
0x180012096  xor     eax, eax
0x180012098  add     rsp, 38h
0x18001209c  pop     r15
0x18001209e  pop     r14
0x1800120a0  pop     r13
0x1800120a2  pop     r12
0x1800120a4  pop     rdi
0x1800120a5  pop     rsi
0x1800120a6  pop     rbp
0x1800120a7  pop     rbx
0x1800120a8  retn
```
