# WindowsMidiServicesInternal::UmpBufferIterator::CopyCurrentMessageToVector(std::vector<uint,std::allocator<uint>> &)

- ea: `0x18000dcc4`
- end: `0x18000ddfc`
- name: `?CopyCurrentMessageToVector@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAXAEAV?$vector@IV?$allocator@I@std@@@std@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(WindowsMidiServicesInternal::UmpBufferIterator *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010650`

## callees

- `0x180003a50`
- `0x18000b344`
- `0x18000cfa4`
- `0x18000dcc4`
- `0x18000de04`

## string_xrefs

- `0x18000ddd9`: `Invalid UMP, incomplete message.`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::UmpBufferIterator::CopyCurrentMessageToVector(
        WindowsMidiServicesInternal::UmpBufferIterator *a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  __int64 v5; // rbx
  int i; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  __int64 result; // rax
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  _DWORD *v19; // r8
  _DWORD *v20; // rdx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = *((_QWORD *)a1 + 2);
  if ( *(_QWORD *)a1 >= v2 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Invalid UMP. Past end of buffer.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v5 = (__int64)(v2 - *(_QWORD *)a1) >> 2;
  if ( (unsigned int)v5 < WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(a1) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Invalid UMP, incomplete message.");
    throw (std::runtime_error *)pExceptionObject;
  }
  for ( i = 0; ; ++i )
  {
    v7 = **(_DWORD **)a1 >> 28;
    if ( v7 <= 8 )
    {
      if ( v7 != 8 )
      {
        if ( !v7 || (v8 = v7 - 1) == 0 || (v9 = v8 - 1) == 0 )
        {
LABEL_13:
          result = 1;
          goto LABEL_24;
        }
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              if ( v12 - 1 <= 1 )
                goto LABEL_13;
LABEL_20:
              result = 0;
              goto LABEL_24;
            }
            goto LABEL_21;
          }
        }
      }
LABEL_23:
      result = 2;
      goto LABEL_24;
    }
    v14 = v7 - 9;
    if ( !v14 )
      goto LABEL_23;
    v15 = v14 - 1;
    if ( !v15 )
      goto LABEL_23;
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 && v18 - 1 >= 2 )
          goto LABEL_20;
LABEL_21:
        result = 4;
        goto LABEL_24;
      }
    }
    result = 3;
LABEL_24:
    if ( i >= (int)result )
      break;
    v19 = (_DWORD *)(*(_QWORD *)a1 + 4LL * i);
    v20 = *(_DWORD **)(a2 + 8);
    if ( v20 == *(_DWORD **)(a2 + 16) )
    {
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(a2, v20, v19);
    }
    else
    {
      *v20 = *v19;
      *(_QWORD *)(a2 + 8) += 4LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dcc4  mov     [rsp+arg_0], rbx
0x18000dcc9  mov     [rsp+arg_8], rsi
0x18000dcce  push    rdi
0x18000dccf  sub     rsp, 40h
0x18000dcd3  mov     rbx, [rcx+10h]
0x18000dcd7  mov     rsi, rdx
0x18000dcda  mov     rdi, rcx
0x18000dcdd  cmp     [rcx], rbx
0x18000dce0  jnb     loc_18000DDB6
0x18000dce6  sub     rbx, [rcx]
0x18000dce9  sar     rbx, 2
0x18000dced  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x18000dcf2  movzx   eax, al
0x18000dcf5  cmp     ebx, eax
0x18000dcf7  jb      loc_18000DDD9
0x18000dcfd  xor     ebx, ebx
0x18000dcff  mov     rdx, [rdi]
0x18000dd02  mov     ecx, [rdx]
0x18000dd04  shr     ecx, 1Ch
0x18000dd07  cmp     ecx, 8
0x18000dd0a  ja      short loc_18000DD3C
0x18000dd0c  jz      short loc_18000DD71
0x18000dd0e  test    ecx, ecx
0x18000dd10  jz      short loc_18000DD35
0x18000dd12  sub     ecx, 1
0x18000dd15  jz      short loc_18000DD35
0x18000dd17  sub     ecx, 1
0x18000dd1a  jz      short loc_18000DD35
0x18000dd1c  sub     ecx, 1
0x18000dd1f  jz      short loc_18000DD71
0x18000dd21  sub     ecx, 1
0x18000dd24  jz      short loc_18000DD71
0x18000dd26  sub     ecx, 1
0x18000dd29  jz      short loc_18000DD63
0x18000dd2b  sub     ecx, 1
0x18000dd2e  jz      short loc_18000DD35
0x18000dd30  cmp     ecx, 1
0x18000dd33  jnz     short loc_18000DD5F
0x18000dd35  mov     eax, 1
0x18000dd3a  jmp     short loc_18000DD76
0x18000dd3c  sub     ecx, 9
0x18000dd3f  jz      short loc_18000DD71
0x18000dd41  sub     ecx, 1
0x18000dd44  jz      short loc_18000DD71
0x18000dd46  sub     ecx, 1
0x18000dd49  jz      short loc_18000DD6A
0x18000dd4b  sub     ecx, 1
0x18000dd4e  jz      short loc_18000DD6A
0x18000dd50  sub     ecx, 1
0x18000dd53  jz      short loc_18000DD63
0x18000dd55  sub     ecx, 1
0x18000dd58  jz      short loc_18000DD63
0x18000dd5a  cmp     ecx, 1
0x18000dd5d  jz      short loc_18000DD63
0x18000dd5f  xor     eax, eax
0x18000dd61  jmp     short loc_18000DD76
0x18000dd63  mov     eax, 4
0x18000dd68  jmp     short loc_18000DD76
0x18000dd6a  mov     eax, 3
0x18000dd6f  jmp     short loc_18000DD76
0x18000dd71  mov     eax, 2
0x18000dd76  cmp     ebx, eax
0x18000dd78  jge     short loc_18000DDA6
0x18000dd7a  movsxd  rax, ebx
0x18000dd7d  lea     r8, [rdx+rax*4]
0x18000dd81  mov     rdx, [rsi+8]
0x18000dd85  cmp     rdx, [rsi+10h]
0x18000dd89  jz      short loc_18000DD97
0x18000dd8b  mov     eax, [r8]
0x18000dd8e  mov     [rdx], eax
0x18000dd90  add     qword ptr [rsi+8], 4
0x18000dd95  jmp     short loc_18000DD9F
0x18000dd97  mov     rcx, rsi
0x18000dd9a  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x18000dd9f  inc     ebx
0x18000dda1  jmp     loc_18000DCFF
0x18000dda6  mov     rbx, [rsp+48h+arg_0]
0x18000ddab  mov     rsi, [rsp+48h+arg_8]
0x18000ddb0  add     rsp, 40h
0x18000ddb4  pop     rdi
0x18000ddb5  retn
0x18000ddb6  lea     rdx, aInvalidUmpPast; "Invalid UMP. Past end of buffer."
0x18000ddbd  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000ddc2  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000ddc7  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000ddce  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000ddd3  call    _CxxThrowException_0
0x18000ddd9  lea     rdx, aInvalidUmpInco; "Invalid UMP, incomplete message."
0x18000dde0  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000dde5  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000ddea  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000ddf1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000ddf6  call    _CxxThrowException_0
```
