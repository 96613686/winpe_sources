# FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)

- ea: `0x18000510c`
- end: `0x1800051ae`
- name: `?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z`
- size: `162`
- prototype: `void __fastcall(struct tagHELPER_ATTRIBUTE *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003670`
- `0x1800067d0`

## callees

- `0x18000510c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000513d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000515d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000519b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000513d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000515d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000519b`

## pseudocode

```c
void __fastcall FreeHelperAttributes(struct tagHELPER_ATTRIBUTE *pv, unsigned int a2, int a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rsi

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      CoTaskMemFree(pv[v7].pwszName);
      pv->pwszName = 0;
      if ( pv[v7].type == AT_STRING )
      {
        CoTaskMemFree(pv[v7].PWStr);
        pv->Int64 = 0;
      }
      else if ( pv[v7].type == AT_OCTET_STRING )
      {
        CoTaskMemFree(pv[v7].OctetString.lpValue);
        pv[v7].OctetString.lpValue = 0;
      }
      ++v6;
      pv[v7++].type = AT_INVALID;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18000510c  test    rcx, rcx
0x18000510f  jz      locret_1800051AD
0x180005115  push    rbx
0x180005116  push    rbp
0x180005117  push    rsi
0x180005118  push    rdi
0x180005119  push    r14
0x18000511b  push    r15
0x18000511d  sub     rsp, 28h
0x180005121  mov     r15d, r8d
0x180005124  mov     r14d, edx
0x180005127  mov     rbx, rcx
0x18000512a  test    edx, edx
0x18000512c  jz      short loc_1800051A1
0x18000512e  xor     ebp, ebp
0x180005130  xor     esi, esi
0x180005132  lea     rdi, [rsi+rsi*8]
0x180005136  add     rdi, rdi
0x180005139  mov     rcx, [rbx+rdi*8]; pv
0x18000513d  call    cs:__imp_CoTaskMemFree
0x180005143  mov     qword ptr [rbx], 0
0x18000514a  cmp     dword ptr [rbx+rdi*8+8], 0Ah
0x18000514f  jz      short loc_18000516E
0x180005151  cmp     dword ptr [rbx+rdi*8+8], 0Eh
0x180005156  jnz     short loc_180005181
0x180005158  mov     rcx, [rbx+rdi*8+18h]; pv
0x18000515d  call    cs:__imp_CoTaskMemFree
0x180005163  mov     qword ptr [rbx+rdi*8+18h], 0
0x18000516c  jmp     short loc_180005181
0x18000516e  mov     rcx, [rbx+rdi*8+10h]; pv
0x180005173  call    cs:__imp_CoTaskMemFree
0x180005179  mov     qword ptr [rbx+10h], 0
0x180005181  inc     ebp
0x180005183  mov     dword ptr [rbx+rdi*8+8], 0
0x18000518b  inc     rsi
0x18000518e  cmp     ebp, r14d
0x180005191  jb      short loc_180005132
0x180005193  test    r15d, r15d
0x180005196  jz      short loc_1800051A1
0x180005198  mov     rcx, rbx; pv
0x18000519b  call    cs:__imp_CoTaskMemFree
0x1800051a1  add     rsp, 28h
0x1800051a5  pop     r15
0x1800051a7  pop     r14
0x1800051a9  pop     rdi
0x1800051aa  pop     rsi
0x1800051ab  pop     rbp
0x1800051ac  pop     rbx
0x1800051ad  retn
```
