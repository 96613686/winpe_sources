# dllmain_crt_dispatch(HINSTANCE__ * const,ulong,void * const)

- ea: `0x10010731`
- end: `0x10010784`
- name: `?dllmain_crt_dispatch@@YGHQAUHINSTANCE__@@KQAX@Z`
- size: `83`
- prototype: `int __stdcall(HINSTANCE, unsigned int, void *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x10010920`

## callees

- `0x10010731`
- `0x10010784`
- `0x1001088e`
- `0x10010daa`
- `0x10010dc9`

## pseudocode

```c
int __stdcall dllmain_crt_dispatch(HINSTANCE a1, unsigned int a2, void *const a3)
{
  int result; // eax

  switch ( a2 )
  {
    case 0u:
      return dllmain_crt_process_detach(a3 != 0);
    case 1u:
      return dllmain_crt_process_attach(a1, a3);
    case 2u:
      LOBYTE(result) = __scrt_dllmain_crt_thread_attach();
      break;
    case 3u:
      LOBYTE(result) = sub_10010DC9();
      break;
    default:
      return 1;
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x10010731  push    ebp
0x10010732  mov     ebp, esp
0x10010734  mov     eax, [ebp+arg_4]
0x10010737  sub     eax, 0
0x1001073a  jz      short loc_1001076F
0x1001073c  sub     eax, 1
0x1001073f  jz      short loc_10010761
0x10010741  sub     eax, 1
0x10010744  jz      short loc_10010757
0x10010746  sub     eax, 1
0x10010749  jz      short loc_10010750
0x1001074b  xor     eax, eax
0x1001074d  inc     eax
0x1001074e  jmp     short loc_10010780
0x10010750  call    sub_10010DC9
0x10010755  jmp     short loc_1001075C
0x10010757  call    ___scrt_dllmain_crt_thread_attach
0x1001075c  movzx   eax, al
0x1001075f  jmp     short loc_10010780
0x10010761  push    [ebp+arg_8]; void *
0x10010764  push    [ebp+arg_0]; HINSTANCE
0x10010767  call    ?dllmain_crt_process_attach@@YAHQAUHINSTANCE__@@QAX@Z
0x1001076c  pop     ecx
0x1001076d  jmp     short loc_1001077F
0x1001076f  cmp     [ebp+arg_8], 0
0x10010773  setnz   al
0x10010776  movzx   eax, al
0x10010779  push    eax; Terminating
0x1001077a  call    ?dllmain_crt_process_detach@@YAH_N@Z
0x1001077f  pop     ecx
0x10010780  pop     ebp
0x10010781  retn    0Ch
```
