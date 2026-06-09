# COMMAND_PROCESSOR::SetLastConfigPropertyException(long,ushort const *,INativePropertyException *,int)

- ea: `0x18000c5e0`
- end: `0x18000c7f9`
- name: `?SetLastConfigPropertyException@COMMAND_PROCESSOR@@UEAAJJPEBGPEAVINativePropertyException@@H@Z`
- size: `537`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, int, const unsigned __int16 *, struct INativePropertyException *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x18000c5e0`
- `0x1800131d8`
- `0x180013288`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::SetLastConfigPropertyException(
        COMMAND_PROCESSOR *this,
        int a2,
        const unsigned __int16 *a3,
        struct INativePropertyException *a4,
        int a5)
{
  int v9; // edi
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  va_list v15; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[32]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+50h] [rbp-B0h]
  __int16 v19; // [rsp+54h] [rbp-ACh]
  int v20; // [rsp+58h] [rbp-A8h]
  va_list Arguments[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int16 v23; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[510]; // [rsp+82h] [rbp-7Eh] BYREF

  v15 = 0;
  *(_OWORD *)Arguments = 0;
  v22 = 0;
  memset_0(v24, 0, sizeof(v24));
  v18 = 512;
  v17 = (unsigned __int16 *)&v23;
  v19 = 256;
  v20 = 0;
  v23 = 0;
  if ( a4 && a3 )
  {
    if ( a5 || !*((_QWORD *)this + 26) )
    {
      v9 = (*(__int64 (__fastcall **)(struct INativePropertyException *, va_list *))(*(_QWORD *)a4 + 80LL))(a4, &v15);
      if ( v9 >= 0 )
      {
        Arguments[1] = v15;
        Arguments[0] = (va_list)a3;
        v9 = FormatCommandMessage(0xC00003ED, Arguments, (struct STRU *)v16);
        if ( v9 >= 0 )
        {
          v9 = StripWhiteSpace((struct STRU *)v16);
          if ( v9 >= 0 )
          {
            v10 = operator new(0x58u);
            v11 = v10;
            if ( v10 )
            {
              *((_DWORD *)v10 + 2) = 1;
              *v10 = &COMMAND_EXCEPTION::`vftable';
              v10[2] = 0;
              v10[6] = v10 + 2;
              *((_DWORD *)v10 + 14) = 32;
              *((_WORD *)v10 + 30) = 256;
              *((_DWORD *)v10 + 16) = 0;
              v10[9] = 0;
              v10[10] = 0;
              v12 = v10[10];
              *((_DWORD *)v10 + 3) = a2;
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              v11[10] = a4;
              (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)a4 + 8LL))(a4);
              v9 = STRU::Copy((STRU *)(v11 + 2), (const unsigned __int8 *)v17);
              if ( v9 < 0 )
              {
                (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
              }
              else
              {
                v13 = *((_QWORD *)this + 26);
                if ( v13 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                *((_QWORD *)this + 26) = v11;
              }
            }
            else
            {
              v9 = -2147024888;
            }
          }
        }
      }
    }
    else
    {
      v9 = 1;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c5e0  mov     [rsp-8+arg_8], rbx
0x18000c5e5  push    rbp
0x18000c5e6  push    rsi
0x18000c5e7  push    rdi
0x18000c5e8  push    r14
0x18000c5ea  push    r15
0x18000c5ec  lea     rbp, [rsp-190h]
0x18000c5f4  sub     rsp, 290h
0x18000c5fb  mov     rax, cs:__security_cookie
0x18000c602  xor     rax, rsp
0x18000c605  mov     [rbp+1B0h+var_30], rax
0x18000c60c  xorps   xmm0, xmm0
0x18000c60f  mov     [rsp+2B0h+var_290], 0
0x18000c618  mov     rbx, r8
0x18000c61b  mov     r15d, edx
0x18000c61e  mov     rsi, rcx
0x18000c621  xor     edx, edx; Val
0x18000c623  mov     r8d, 1FEh; Size
0x18000c629  lea     rcx, [rbp+1B0h+var_22E]; void *
0x18000c62d  movups  xmmword ptr [rsp+2B0h+Arguments], xmm0
0x18000c632  mov     r14, r9
0x18000c635  movups  [rsp+2B0h+var_240], xmm0
0x18000c63a  call    memset_0
0x18000c63f  lea     rax, [rbp+1B0h+var_230]
0x18000c643  mov     [rsp+2B0h+var_260], 200h
0x18000c64b  mov     [rsp+2B0h+var_268], rax
0x18000c650  xor     eax, eax
0x18000c652  mov     [rsp+2B0h+var_25C], 100h
0x18000c659  mov     [rsp+2B0h+var_258], 0
0x18000c661  mov     [rbp+1B0h+var_230], ax
0x18000c665  test    r14, r14
0x18000c668  jz      loc_18000C7C2
0x18000c66e  test    rbx, rbx
0x18000c671  jz      loc_18000C7C2
0x18000c677  cmp     [rbp+1B0h+arg_20], eax
0x18000c67d  jnz     short loc_18000C690
0x18000c67f  cmp     [rsi+0D0h], rax
0x18000c686  jz      short loc_18000C690
0x18000c688  lea     edi, [rax+1]
0x18000c68b  jmp     loc_18000C7C7
0x18000c690  mov     rax, [r14]
0x18000c693  lea     rdx, [rsp+2B0h+var_290]
0x18000c698  mov     rcx, r14
0x18000c69b  mov     rax, [rax+50h]
0x18000c69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6a4  mov     edi, eax
0x18000c6a6  test    eax, eax
0x18000c6a8  js      loc_18000C7C7
0x18000c6ae  mov     rax, [rsp+2B0h+var_290]
0x18000c6b3  lea     r8, [rsp+2B0h+var_288]; this
0x18000c6b8  lea     rdx, [rsp+2B0h+Arguments]; Arguments
0x18000c6bd  mov     [rsp+2B0h+Arguments+8], rax
0x18000c6c2  mov     ecx, 0C00003EDh; dwMessageId
0x18000c6c7  mov     [rsp+2B0h+Arguments], rbx
0x18000c6cc  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x18000c6d1  mov     edi, eax
0x18000c6d3  test    eax, eax
0x18000c6d5  js      loc_18000C7C7
0x18000c6db  lea     rcx, [rsp+2B0h+var_288]; this
0x18000c6e0  call    ?StripWhiteSpace@@YAJPEAVSTRU@@@Z; StripWhiteSpace(STRU *)
0x18000c6e5  mov     edi, eax
0x18000c6e7  test    eax, eax
0x18000c6e9  js      loc_18000C7C7
0x18000c6ef  mov     ecx, 58h ; 'X'; Size
0x18000c6f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c6f9  mov     rbx, rax
0x18000c6fc  test    rax, rax
0x18000c6ff  jz      loc_18000C7BB
0x18000c705  mov     dword ptr [rbx+8], 1
0x18000c70c  lea     rcx, [rbx+10h]
0x18000c710  lea     rax, ??_7COMMAND_EXCEPTION@@6B@; const COMMAND_EXCEPTION::`vftable'
0x18000c717  mov     [rbx], rax
0x18000c71a  mov     qword ptr [rcx], 0
0x18000c721  mov     [rcx+20h], rcx
0x18000c725  mov     dword ptr [rcx+28h], 20h ; ' '
0x18000c72c  mov     word ptr [rcx+2Ch], 100h
0x18000c732  mov     dword ptr [rcx+30h], 0
0x18000c739  mov     qword ptr [rbx+48h], 0
0x18000c741  mov     qword ptr [rbx+50h], 0
0x18000c749  mov     rcx, [rbx+50h]
0x18000c74d  mov     [rbx+0Ch], r15d
0x18000c751  test    rcx, rcx
0x18000c754  jz      short loc_18000C762
0x18000c756  mov     rax, [rcx]
0x18000c759  mov     rax, [rax+10h]
0x18000c75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c762  mov     [rbx+50h], r14
0x18000c766  mov     rcx, r14
0x18000c769  mov     rax, [r14]
0x18000c76c  mov     rax, [rax+8]
0x18000c770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c775  mov     rdx, [rsp+2B0h+var_268]; unsigned __int16 *
0x18000c77a  lea     rcx, [rbx+10h]; this
0x18000c77e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c783  mov     edi, eax
0x18000c785  test    eax, eax
0x18000c787  js      short loc_18000C7AA
0x18000c789  mov     rcx, [rsi+0D0h]
0x18000c790  test    rcx, rcx
0x18000c793  jz      short loc_18000C7A1
0x18000c795  mov     rax, [rcx]
0x18000c798  mov     rax, [rax+10h]
0x18000c79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7a1  mov     [rsi+0D0h], rbx
0x18000c7a8  jmp     short loc_18000C7C7
0x18000c7aa  mov     rax, [rbx]
0x18000c7ad  mov     rcx, rbx
0x18000c7b0  mov     rax, [rax+10h]
0x18000c7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b9  jmp     short loc_18000C7C7
0x18000c7bb  mov     edi, 80070008h
0x18000c7c0  jmp     short loc_18000C7C7
0x18000c7c2  mov     edi, 80070057h
0x18000c7c7  lea     rcx, [rsp+2B0h+var_288]; this
0x18000c7cc  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000c7d1  mov     eax, edi
0x18000c7d3  mov     rcx, [rbp+1B0h+var_30]
0x18000c7da  xor     rcx, rsp; StackCookie
0x18000c7dd  call    __security_check_cookie
0x18000c7e2  mov     rbx, [rsp+2B0h+arg_8]
0x18000c7ea  add     rsp, 290h
0x18000c7f1  pop     r15
0x18000c7f3  pop     r14
0x18000c7f5  pop     rdi
0x18000c7f6  pop     rsi
0x18000c7f7  pop     rbp
0x18000c7f8  retn
```
