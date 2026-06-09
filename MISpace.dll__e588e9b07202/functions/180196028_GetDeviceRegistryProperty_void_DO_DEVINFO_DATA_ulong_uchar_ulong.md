# GetDeviceRegistryProperty(void *,_DO_DEVINFO_DATA *,ulong,uchar * *,ulong)

- ea: `0x180196028`
- end: `0x1801961ea`
- name: `?GetDeviceRegistryProperty@@YAKPEAXPEAU_DO_DEVINFO_DATA@@KPEAPEAEK@Z`
- size: `450`
- prototype: `unsigned int __fastcall(void *, struct _DO_DEVINFO_DATA *, unsigned int, unsigned __int8 **, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18019d09c`

## callees

- `0x180196028`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801960aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019614f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019618d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801960aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019614f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019618d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801960d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801961b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801960d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801961b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801960c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801960ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801961a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801960c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801960ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801961a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180196106`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180196106`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1801960a2`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019613f`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180196183`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1801960a2`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019613f`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180196183`

## pseudocode

```c
DWORD __fastcall GetDeviceRegistryProperty(void *a1, struct _DO_DEVINFO_DATA *a2, __int64 a3, unsigned __int8 **a4)
{
  DWORD result; // eax
  int DeviceRegistryProperty; // ebx
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  unsigned __int8 *v12; // rax

  if ( !a4 )
    return 87;
  while ( 1 )
  {
    DeviceRegistryProperty = DevObjGetDeviceRegistryProperty(a1, a2, 12);
    result = GetLastError();
    if ( !DeviceRegistryProperty && result != 122 )
      break;
    v9 = *a4;
    if ( *a4 )
    {
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
        HeapFree(ProcessHeap, 0, v9);
      *a4 = 0;
    }
    v11 = GetProcessHeap();
    if ( !v11 )
    {
      *a4 = 0;
      return 8;
    }
    v12 = (unsigned __int8 *)HeapAlloc(v11, 8u, 0);
    *a4 = v12;
    if ( !v12 )
      return 8;
    if ( !(unsigned int)DevObjGetDeviceRegistryProperty(a1, a2, 12) )
      GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x180196028  mov     rax, rsp
0x18019602b  mov     [rax+8], rbx
0x18019602f  mov     [rax+10h], rbp
0x180196033  mov     [rax+18h], r8d
0x180196037  push    rsi
0x180196038  push    rdi
0x180196039  push    r12
0x18019603b  push    r14
0x18019603d  push    r15
0x18019603f  sub     rsp, 40h
0x180196043  mov     dword ptr [rax+18h], 0
0x18019604a  mov     rdi, r9
0x18019604d  mov     r15, rdx
0x180196050  mov     r12, rcx
0x180196053  test    r9, r9
0x180196056  jnz     short loc_180196061
0x180196058  lea     eax, [r9+57h]
0x18019605c  jmp     loc_1801961D3
0x180196061  xor     esi, esi
0x180196063  xor     ebx, ebx
0x180196065  xor     ebp, ebp
0x180196067  xor     r14b, r14b
0x18019606a  test    esi, esi
0x18019606c  jz      short loc_180196077
0x18019606e  cmp     ebx, 7Ah ; 'z'
0x180196071  jnz     loc_18019615C
0x180196077  xor     r9d, r9d
0x18019607a  lea     rax, [rsp+68h+dwBytes]
0x180196082  mov     [rsp+68h+var_38], rax
0x180196087  mov     rdx, r15
0x18019608a  mov     [rsp+68h+var_40], 0
0x180196092  mov     rcx, r12
0x180196095  mov     [rsp+68h+var_48], 0
0x18019609e  lea     r8d, [r9+0Ch]
0x1801960a2  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x1801960a8  mov     ebx, eax
0x1801960aa  call    cs:__imp_GetLastError
0x1801960b0  test    ebx, ebx
0x1801960b2  jnz     short loc_1801960BD
0x1801960b4  cmp     eax, 7Ah ; 'z'
0x1801960b7  jnz     loc_1801961D3
0x1801960bd  mov     rbx, [rdi]
0x1801960c0  test    rbx, rbx
0x1801960c3  jz      short loc_1801960E5
0x1801960c5  call    cs:__imp_GetProcessHeap
0x1801960cb  test    rax, rax
0x1801960ce  jz      short loc_1801960DE
0x1801960d0  mov     r8, rbx; lpMem
0x1801960d3  xor     edx, edx; dwFlags
0x1801960d5  mov     rcx, rax; hHeap
0x1801960d8  call    cs:__imp_HeapFree
0x1801960de  mov     qword ptr [rdi], 0
0x1801960e5  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x1801960ec  call    cs:__imp_GetProcessHeap
0x1801960f2  test    rax, rax
0x1801960f5  jz      loc_1801961C7
0x1801960fb  mov     r8d, ebx; dwBytes
0x1801960fe  mov     edx, 8; dwFlags
0x180196103  mov     rcx, rax; hHeap
0x180196106  call    cs:__imp_HeapAlloc
0x18019610c  mov     [rdi], rax
0x18019610f  test    rax, rax
0x180196112  jz      loc_1801961CE
0x180196118  mov     esi, dword ptr [rsp+68h+dwBytes]
0x18019611f  xor     ebx, ebx
0x180196121  mov     [rsp+68h+var_38], rbx
0x180196126  xor     r9d, r9d
0x180196129  mov     [rsp+68h+var_40], esi
0x18019612d  mov     rdx, r15
0x180196130  mov     rcx, r12
0x180196133  mov     [rsp+68h+var_48], rax
0x180196138  lea     r8d, [rbx+0Ch]
0x18019613c  mov     r14b, 1
0x18019613f  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180196145  mov     ebp, eax
0x180196147  test    eax, eax
0x180196149  jnz     loc_18019606A
0x18019614f  call    cs:__imp_GetLastError
0x180196155  mov     ebx, eax
0x180196157  jmp     loc_18019606A
0x18019615c  test    r14b, r14b
0x18019615f  jnz     short loc_180196197
0x180196161  mov     rax, [rdi]
0x180196164  xor     r9d, r9d
0x180196167  mov     [rsp+68h+var_38], 0
0x180196170  mov     rdx, r15
0x180196173  mov     [rsp+68h+var_40], esi
0x180196177  mov     rcx, r12
0x18019617a  mov     [rsp+68h+var_48], rax
0x18019617f  lea     r8d, [r9+0Ch]
0x180196183  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180196189  test    eax, eax
0x18019618b  jnz     short loc_1801961C3
0x18019618d  call    cs:__imp_GetLastError
0x180196193  mov     ebx, eax
0x180196195  jmp     short loc_1801961C3
0x180196197  test    ebp, ebp
0x180196199  jnz     short loc_1801961C3
0x18019619b  mov     rsi, [rdi]
0x18019619e  test    rsi, rsi
0x1801961a1  jz      short loc_1801961C3
0x1801961a3  call    cs:__imp_GetProcessHeap
0x1801961a9  test    rax, rax
0x1801961ac  jz      short loc_1801961BC
0x1801961ae  mov     r8, rsi; lpMem
0x1801961b1  xor     edx, edx; dwFlags
0x1801961b3  mov     rcx, rax; hHeap
0x1801961b6  call    cs:__imp_HeapFree
0x1801961bc  mov     qword ptr [rdi], 0
0x1801961c3  mov     eax, ebx
0x1801961c5  jmp     short loc_1801961D3
0x1801961c7  mov     qword ptr [rdi], 0
0x1801961ce  mov     eax, 8
0x1801961d3  mov     rbx, [rsp+68h+arg_0]
0x1801961d8  mov     rbp, [rsp+68h+arg_8]
0x1801961dd  add     rsp, 40h
0x1801961e1  pop     r15
0x1801961e3  pop     r14
0x1801961e5  pop     r12
0x1801961e7  pop     rdi
0x1801961e8  pop     rsi
0x1801961e9  retn
```
