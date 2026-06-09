# CBdeCfgSecureFormat::Thread_WipeAndFormatVolume(void)

- ea: `0x18000d29c`
- end: `0x18000d4ae`
- name: `?Thread_WipeAndFormatVolume@CBdeCfgSecureFormat@@AEAAJXZ`
- size: `530`
- prototype: `__int64 __fastcall(CBdeCfgSecureFormat *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d780`

## callees

- `0x18000d29c`
- `0x18000d510`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000d485`
- `ole32!CoTaskMemFree` at `0x1800141f7`
- `ole32!CoTaskMemFree` at `0x18000d485`
- `ole32!CoTaskMemFree` at `0x1800141f7`

## pseudocode

```c
__int64 __fastcall CBdeCfgSecureFormat::Thread_WipeAndFormatVolume(CBdeCfgSecureFormat *this)
{
  int v2; // ebx
  __int64 v4; // [rsp+58h] [rbp-80h] BYREF
  __int64 v5; // [rsp+60h] [rbp-78h]
  int v6; // [rsp+68h] [rbp-70h] BYREF
  _OWORD v7[2]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v8[32]; // [rsp+90h] [rbp-48h] BYREF
  __int128 v9; // [rsp+B0h] [rbp-28h]
  LPVOID pv; // [rsp+C0h] [rbp-18h]

  v4 = 0;
  v6 = 0;
  v5 = 0;
  memset(v7, 0, sizeof(v7));
  memset(v8, 0, sizeof(v8));
  v9 = 0;
  pv = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4), v8);
  if ( v2 >= 0 )
  {
    if ( (WORD4(v9) & 0x2000) != 0 )
    {
      v2 = -1063256048;
    }
    else
    {
      v2 = CBdeCfgSecureFormat::Wipe(this, (unsigned __int16 *)pv, v9);
      if ( v2 >= 0 )
      {
        v2 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 4))(
               *((_QWORD *)this + 4),
               &IID_IVdsVolumeMF,
               &v4);
        if ( v2 >= 0 )
        {
          if ( *((_BYTE *)this + 16) )
          {
            v2 = -1063256047;
          }
          else
          {
            v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(__int64, __int64, const OLECHAR *))(*(_QWORD *)v4 + 32LL))(
                     v4,
                     4,
                     &word_180017638);
              if ( v2 >= 0 )
              {
                v2 = (*(__int64 (__fastcall **)(__int64, int *, _OWORD *))(*(_QWORD *)v5 + 32LL))(v5, &v6, v7);
                if ( v2 >= 0 )
                {
                  if ( v6 >= 0 )
                    *((_DWORD *)this + 3) = 100;
                  else
                    v2 = v6;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v4 = 0;
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v5 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d29c  mov     r11, rsp
0x18000d29f  mov     [r11+10h], rbx
0x18000d2a3  push    rdi
0x18000d2a4  sub     rsp, 0D0h
0x18000d2ab  mov     rax, cs:__security_cookie
0x18000d2b2  xor     rax, rsp
0x18000d2b5  mov     [rsp+0D8h+var_10], rax
0x18000d2bd  mov     rdi, rcx
0x18000d2c0  mov     qword ptr [r11-80h], 0
0x18000d2c8  mov     [rsp+0D8h+var_70], 0
0x18000d2d0  mov     qword ptr [r11-78h], 0
0x18000d2d8  xorps   xmm0, xmm0
0x18000d2db  movups  [rsp+0D8h+var_68], xmm0
0x18000d2e0  movups  xmmword ptr [r11-58h], xmm0
0x18000d2e5  xorps   xmm1, xmm1
0x18000d2e8  xor     eax, eax
0x18000d2ea  movups  xmmword ptr [r11-48h], xmm1
0x18000d2ef  movups  xmmword ptr [r11-38h], xmm1
0x18000d2f4  movups  xmmword ptr [r11-28h], xmm1
0x18000d2f9  mov     [r11-18h], rax
0x18000d2fd  mov     rcx, [rcx+20h]
0x18000d301  mov     rax, [rcx]
0x18000d304  lea     rdx, [r11-48h]
0x18000d308  mov     rax, [rax+18h]
0x18000d30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d311  mov     ebx, eax
0x18000d313  mov     [rsp+0D8h+var_88], eax
0x18000d317  test    eax, eax
0x18000d319  js      loc_18000D43A
0x18000d31f  test    [rsp+0D8h+var_20], 2000h
0x18000d32a  jz      short loc_18000D33A
0x18000d32c  mov     ebx, 0C0A00010h
0x18000d331  mov     [rsp+0D8h+var_88], ebx
0x18000d335  jmp     loc_18000D43A
0x18000d33a  mov     r8, [rsp+0D8h+var_28]; unsigned __int64
0x18000d342  mov     rdx, [rsp+0D8h+pv]; unsigned __int16 *
0x18000d34a  mov     rcx, rdi; this
0x18000d34d  call    ?Wipe@CBdeCfgSecureFormat@@AEAAJPEAG_K@Z; CBdeCfgSecureFormat::Wipe(ushort *,unsigned __int64)
0x18000d352  mov     ebx, eax
0x18000d354  mov     [rsp+0D8h+var_88], eax
0x18000d358  test    eax, eax
0x18000d35a  js      loc_18000D43A
0x18000d360  mov     rcx, [rdi+20h]
0x18000d364  mov     rax, [rcx]
0x18000d367  lea     r8, [rsp+0D8h+var_80]
0x18000d36c  lea     rdx, IID_IVdsVolumeMF
0x18000d373  mov     rax, [rax]
0x18000d376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37b  mov     ebx, eax
0x18000d37d  mov     [rsp+0D8h+var_88], eax
0x18000d381  test    eax, eax
0x18000d383  js      loc_18000D43A
0x18000d389  mov     al, [rdi+10h]
0x18000d38c  test    al, al
0x18000d38e  jz      short loc_18000D397
0x18000d390  mov     ebx, 0C0A00011h
0x18000d395  jmp     short loc_18000D331
0x18000d397  mov     rcx, [rsp+0D8h+var_80]
0x18000d39c  mov     rax, [rcx]
0x18000d39f  mov     rax, [rax+48h]
0x18000d3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a8  mov     ebx, eax
0x18000d3aa  mov     [rsp+0D8h+var_88], eax
0x18000d3ae  test    eax, eax
0x18000d3b0  js      loc_18000D43A
0x18000d3b6  mov     rcx, [rsp+0D8h+var_80]
0x18000d3bb  mov     rax, [rcx]
0x18000d3be  lea     rdx, [rsp+0D8h+var_78]
0x18000d3c3  mov     [rsp+0D8h+var_A0], rdx
0x18000d3c8  mov     [rsp+0D8h+var_A8], 0
0x18000d3d0  mov     edx, 1
0x18000d3d5  mov     [rsp+0D8h+var_B0], edx
0x18000d3d9  mov     [rsp+0D8h+var_B8], edx
0x18000d3dd  xor     r9d, r9d
0x18000d3e0  lea     r8, word_180017638
0x18000d3e7  lea     edx, [r9+4]
0x18000d3eb  mov     rax, [rax+20h]
0x18000d3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f4  mov     ebx, eax
0x18000d3f6  mov     [rsp+0D8h+var_88], eax
0x18000d3fa  test    eax, eax
0x18000d3fc  js      short loc_18000D43A
0x18000d3fe  mov     rcx, [rsp+0D8h+var_78]
0x18000d403  mov     rax, [rcx]
0x18000d406  lea     r8, [rsp+0D8h+var_68]
0x18000d40b  lea     rdx, [rsp+0D8h+var_70]
0x18000d410  mov     rax, [rax+20h]
0x18000d414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d419  mov     ebx, eax
0x18000d41b  mov     [rsp+0D8h+var_88], eax
0x18000d41f  test    eax, eax
0x18000d421  js      short loc_18000D43A
0x18000d423  mov     eax, [rsp+0D8h+var_70]
0x18000d427  test    eax, eax
0x18000d429  jns     short loc_18000D433
0x18000d42b  mov     ebx, eax
0x18000d42d  mov     [rsp+0D8h+var_88], eax
0x18000d431  jmp     short loc_18000D43A
0x18000d433  mov     dword ptr [rdi+0Ch], 64h ; 'd'
0x18000d43a  mov     rcx, [rsp+0D8h+var_80]
0x18000d43f  test    rcx, rcx
0x18000d442  jz      short loc_18000D459
0x18000d444  mov     rax, [rcx]
0x18000d447  mov     rax, [rax+10h]
0x18000d44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d450  mov     [rsp+0D8h+var_80], 0
0x18000d459  mov     rcx, [rsp+0D8h+var_78]
0x18000d45e  test    rcx, rcx
0x18000d461  jz      short loc_18000D478
0x18000d463  mov     rax, [rcx]
0x18000d466  mov     rax, [rax+10h]
0x18000d46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d46f  mov     [rsp+0D8h+var_78], 0
0x18000d478  mov     rcx, [rsp+0D8h+pv]; pv
0x18000d480  test    rcx, rcx
0x18000d483  jz      short loc_18000D48B
0x18000d485  call    cs:__imp_CoTaskMemFree
0x18000d48b  mov     eax, ebx
0x18000d48d  mov     rcx, [rsp+0D8h+var_10]
0x18000d495  xor     rcx, rsp; StackCookie
0x18000d498  call    __security_check_cookie
0x18000d49d  mov     rbx, [rsp+0D8h+arg_8]
0x18000d4a5  add     rsp, 0D0h
0x18000d4ac  pop     rdi
0x18000d4ad  retn
0x1800141a8  push    rbp
0x1800141aa  sub     rsp, 50h
0x1800141ae  mov     rbp, rdx
0x1800141b1  mov     rcx, [rbp+58h]
0x1800141b5  test    rcx, rcx
0x1800141b8  jz      short loc_1800141CE
0x1800141ba  mov     rax, [rcx]
0x1800141bd  mov     rax, [rax+10h]
0x1800141c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141c6  mov     qword ptr [rbp+58h], 0
0x1800141ce  mov     rcx, [rbp+60h]
0x1800141d2  test    rcx, rcx
0x1800141d5  jz      short loc_1800141EB
0x1800141d7  mov     rax, [rcx]
0x1800141da  mov     rax, [rax+10h]
0x1800141de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141e3  mov     qword ptr [rbp+60h], 0
0x1800141eb  mov     rcx, [rbp+0C0h]; pv
0x1800141f2  test    rcx, rcx
0x1800141f5  jz      short loc_1800141FE
0x1800141f7  call    cs:__imp_CoTaskMemFree
0x1800141fd  nop
0x1800141fe  add     rsp, 50h
0x180014202  pop     rbp
0x180014203  retn
```
