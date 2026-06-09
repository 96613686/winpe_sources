# _attributes_array_t::FreeAll(void)

- ea: `0x180005050`
- end: `0x1800050f4`
- name: `?FreeAll@_attributes_array_t@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(_attributes_array_t *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800036d0`
- `0x1800037e8`
- `0x180005910`
- `0x18000bb08`
- `0x18000bfe0`

## callees

- `0x180005050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050d7`

## pseudocode

```c
void __fastcall _attributes_array_t::FreeAll(_attributes_array_t *this)
{
  __int64 i; // rbp
  __int64 v3; // rsi
  __int64 v4; // rdi

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; *(_QWORD *)(v3 + 8 * v4) = 0 )
    {
      v3 = *((_QWORD *)this + 1);
      v4 = 18 * i;
      if ( *(_DWORD *)(v3 + 144 * i + 8) == 10 )
      {
        CoTaskMemFree(*(LPVOID *)(v3 + 144 * i + 16));
        *(_QWORD *)(v3 + 144 * i + 16) = 0;
      }
      else if ( *(_DWORD *)(v3 + 144 * i + 8) == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v3 + 144 * i + 24));
        *(_QWORD *)(v3 + 144 * i + 24) = 0;
        *(_DWORD *)(v3 + 144 * i + 16) = 0;
      }
      CoTaskMemFree(*(LPVOID *)(v3 + 144 * i));
      i = (unsigned int)(i + 1);
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 1));
  *((_QWORD *)this + 1) = 0;
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x180005050  push    rbx
0x180005052  push    rbp
0x180005053  push    rsi
0x180005054  push    rdi
0x180005055  sub     rsp, 28h
0x180005059  cmp     qword ptr [rcx+8], 0
0x18000505e  mov     rbx, rcx
0x180005061  jz      short loc_1800050D3
0x180005063  xor     ebp, ebp
0x180005065  cmp     [rcx], ebp
0x180005067  jbe     short loc_1800050D3
0x180005069  mov     rsi, [rbx+8]
0x18000506d  lea     rdi, ds:0[rbp*8]
0x180005075  add     rdi, rbp
0x180005078  add     rdi, rdi
0x18000507b  cmp     dword ptr [rsi+rdi*8+8], 0Ah
0x180005080  jnz     short loc_180005098
0x180005082  mov     rcx, [rsi+rdi*8+10h]; pv
0x180005087  call    cs:__imp_CoTaskMemFree
0x18000508d  mov     qword ptr [rsi+rdi*8+10h], 0
0x180005096  jmp     short loc_1800050BB
0x180005098  cmp     dword ptr [rsi+rdi*8+8], 0Eh
0x18000509d  jnz     short loc_1800050BB
0x18000509f  mov     rcx, [rsi+rdi*8+18h]; pv
0x1800050a4  call    cs:__imp_CoTaskMemFree
0x1800050aa  mov     qword ptr [rsi+rdi*8+18h], 0
0x1800050b3  mov     dword ptr [rsi+rdi*8+10h], 0
0x1800050bb  mov     rcx, [rsi+rdi*8]; pv
0x1800050bf  call    cs:__imp_CoTaskMemFree
0x1800050c5  inc     ebp
0x1800050c7  mov     qword ptr [rsi+rdi*8], 0
0x1800050cf  cmp     ebp, [rbx]
0x1800050d1  jb      short loc_180005069
0x1800050d3  mov     rcx, [rbx+8]; pv
0x1800050d7  call    cs:__imp_CoTaskMemFree
0x1800050dd  mov     qword ptr [rbx+8], 0
0x1800050e5  mov     dword ptr [rbx], 0
0x1800050eb  add     rsp, 28h
0x1800050ef  pop     rdi
0x1800050f0  pop     rsi
0x1800050f1  pop     rbp
0x1800050f2  pop     rbx
0x1800050f3  retn
```
