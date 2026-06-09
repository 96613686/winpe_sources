# CSLSResponse::GetData(char * *,ulong *)

- ea: `0x140033e34`
- end: `0x140033f58`
- name: `?GetData@CSLSResponse@@QEAAJPEAPEADPEAK@Z`
- size: `292`
- prototype: `__int64 __fastcall(CSLSResponse *__hidden this, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140024f14`

## callees

- `0x140033e34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140033f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033e83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140033e83`

## pseudocode

```c
__int64 __fastcall CSLSResponse::GetData(CSLSResponse *this, char **a2, unsigned int *a3)
{
  int v5; // ebx
  char *v6; // rcx
  __int64 v8; // r8
  unsigned int v9; // edx
  __int64 v10; // rsi
  unsigned __int64 v11; // r9
  __int64 v12; // r8
  char *v13; // rdx
  __int64 v14; // r10
  char v15; // al
  char *v16; // rax
  signed int v17; // eax

  v5 = 0;
  v6 = 0;
  v8 = *((_QWORD *)this + 6);
  if ( v8 && (v9 = *((_DWORD *)this + 14)) != 0 )
  {
    if ( *(_BYTE *)(v9 - 1 + v8) )
      ++v9;
    v10 = v9;
    v6 = (char *)CoTaskMemAlloc(v9);
    if ( !v6 )
    {
      v5 = -2147024882;
      goto LABEL_22;
    }
    v11 = *((unsigned int *)this + 14);
    if ( (unsigned __int64)(v10 - 1) > 0x7FFFFFFE )
    {
      v5 = -2147024809;
      v17 = -2147024809;
      if ( v10 )
      {
        *v6 = 0;
        goto LABEL_22;
      }
    }
    else
    {
      if ( v11 > 0x7FFFFFFE )
      {
        *v6 = 0;
        v5 = -2147024809;
        goto LABEL_22;
      }
      v12 = v10;
      v13 = v6;
      v14 = *((_QWORD *)this + 6) - (_QWORD)v6;
      do
      {
        if ( !v11 )
          break;
        v15 = v13[v14];
        if ( !v15 )
          break;
        *v13 = v15;
        --v11;
        ++v13;
        --v12;
      }
      while ( v12 );
      v16 = v13 - 1;
      if ( v12 )
        v16 = v13;
      *v16 = 0;
      v17 = v12 == 0 ? 0x8007007A : 0;
    }
    v5 = v17;
    if ( v17 >= 0 )
    {
      *a3 = v10;
      *a2 = v6;
      v6 = 0;
    }
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
LABEL_22:
  CoTaskMemFree(v6);
  if ( v5 < 0 )
  {
    *a2 = 0;
    *a3 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140033e34  mov     rax, rsp
0x140033e37  mov     [rax+8], rbx
0x140033e3b  mov     [rax+10h], rsi
0x140033e3f  mov     [rax+18h], rdi
0x140033e43  mov     [rax+20h], r14
0x140033e47  push    r15
0x140033e49  sub     rsp, 20h
0x140033e4d  mov     rdi, rcx
0x140033e50  mov     r14, r8
0x140033e53  xor     ebx, ebx
0x140033e55  xor     ecx, ecx; pv
0x140033e57  mov     r15, rdx
0x140033e5a  mov     r8, [rdi+30h]
0x140033e5e  test    r8, r8
0x140033e61  jz      loc_140033F1D
0x140033e67  mov     edx, [rdi+38h]
0x140033e6a  test    edx, edx
0x140033e6c  jz      loc_140033F1D
0x140033e72  lea     ecx, [rdx-1]
0x140033e75  cmp     [rcx+r8], bl
0x140033e79  lea     eax, [rdx+1]
0x140033e7c  cmovnz  edx, eax
0x140033e7f  mov     ecx, edx; cb
0x140033e81  mov     esi, edx
0x140033e83  call    cs:__imp_CoTaskMemAlloc
0x140033e89  mov     rcx, rax
0x140033e8c  test    rax, rax
0x140033e8f  jnz     short loc_140033E9B
0x140033e91  mov     ebx, 8007000Eh
0x140033e96  jmp     loc_140033F23
0x140033e9b  mov     r9d, [rdi+38h]
0x140033e9f  lea     rax, [rsi-1]
0x140033ea3  mov     r10, [rdi+30h]
0x140033ea7  mov     edx, 7FFFFFFEh
0x140033eac  cmp     rax, rdx
0x140033eaf  ja      short loc_140033F0C
0x140033eb1  cmp     r9, rdx
0x140033eb4  jbe     short loc_140033EBF
0x140033eb6  mov     [rcx], bl
0x140033eb8  mov     ebx, 80070057h
0x140033ebd  jmp     short loc_140033F23
0x140033ebf  mov     r8, rsi
0x140033ec2  mov     rdx, rcx
0x140033ec5  sub     r10, rcx
0x140033ec8  test    r9, r9
0x140033ecb  jz      short loc_140033EE3
0x140033ecd  mov     al, [r10+rdx]
0x140033ed1  test    al, al
0x140033ed3  jz      short loc_140033EE3
0x140033ed5  mov     [rdx], al
0x140033ed7  dec     r9
0x140033eda  inc     rdx
0x140033edd  sub     r8, 1
0x140033ee1  jnz     short loc_140033EC8
0x140033ee3  test    r8, r8
0x140033ee6  lea     rax, [rdx-1]
0x140033eea  cmovnz  rax, rdx
0x140033eee  neg     r8
0x140033ef1  mov     [rax], bl
0x140033ef3  sbb     eax, eax
0x140033ef5  not     eax
0x140033ef7  and     eax, 8007007Ah
0x140033efc  mov     ebx, eax
0x140033efe  test    eax, eax
0x140033f00  js      short loc_140033F23
0x140033f02  mov     [r14], esi
0x140033f05  mov     [r15], rcx
0x140033f08  xor     ecx, ecx
0x140033f0a  jmp     short loc_140033F23
0x140033f0c  mov     ebx, 80070057h
0x140033f11  mov     eax, ebx
0x140033f13  test    rsi, rsi
0x140033f16  jz      short loc_140033EFC
0x140033f18  mov     byte ptr [rcx], 0
0x140033f1b  jmp     short loc_140033F23
0x140033f1d  mov     [r15], rcx
0x140033f20  mov     [r14], ecx
0x140033f23  call    cs:__imp_CoTaskMemFree
0x140033f29  test    ebx, ebx
0x140033f2b  jns     short loc_140033F3B
0x140033f2d  mov     qword ptr [r15], 0
0x140033f34  mov     dword ptr [r14], 0
0x140033f3b  mov     rsi, [rsp+28h+arg_8]
0x140033f40  mov     eax, ebx
0x140033f42  mov     rbx, [rsp+28h+arg_0]
0x140033f47  mov     rdi, [rsp+28h+arg_10]
0x140033f4c  mov     r14, [rsp+28h+arg_18]
0x140033f51  add     rsp, 20h
0x140033f55  pop     r15
0x140033f57  retn
```
